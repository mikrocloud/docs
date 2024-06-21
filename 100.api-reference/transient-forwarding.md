---
title: "Transient Port Forwarding"
---

This document explains how to manage transient port forwarding for your MikroTik routers using the provided API
endpoints. This feature allows temporary port forwarding over the
existing [management tunnel](/documentation/deployments/management-vpn), which is useful for accessing LAN devices
behind a router that might not have a public IP address.

## Retrieve Active Port Forwards

The `/api/routers/{router_id}/transient-forwarding` endpoint allows you to retrieve all active port forwards for the
specified router.

### Endpoint

`GET` `/api/routers/{router_id}/transient-forwarding`

### Sample Response

```json
[
  {
    "id": "12345678-1234-1234-1234-123456789012",
    "port": 49159,
    "revoked_early": false,
    "allow_only_cidr": "198.51.100.0/24",
    "authorized_at": null,
    "expires_at": "2024-06-22T04:33:29+00:00",
    "expired": false,
    "entry_point": "us-east1.mkcld.io",
    "dst_address": "192.168.88.43",
    "dst_port": 22,
    "time_to_expire": "1 hour from now"
  }
  // Additional data points...
]
```

### Transient Port Forwarding Object

| Property          | Type    | Description                                                                                    |
|-------------------|---------|------------------------------------------------------------------------------------------------|
| `id`              | string  | The unique identifier for the transient port forward.                                          |
| `port`            | number  | The external port that the user connects to, which is forwarded to `dst_port`.                 |
| `revoked_early`   | boolean | Indicates if the port forward was revoked before expiration.                                   |
| `allow_only_cidr` | string  | The CIDR range of IP addresses allowed to use this port forward.                               |
| `authorized_at`   | string  | The timestamp of when the port forward was authorized (currently not in use).                  |
| `expires_at`      | string  | The UTC timestamp when the port forward will expire and be removed.                            |
| `expired`         | boolean | Indicates if the port forward has expired.                                                     |
| `entry_point`     | string  | [Regional server](/documentation/resources/regional-servers) entry point for the port forward. |
| `dst_address`     | string  | The IP address that the port is being forwarded to.                                            |
| `dst_port`        | number  | The port on the device behind the MikroTik router that receives the forwarded traffic.         |
| `time_to_expire`  | string  | The remaining time until the port forward expires.                                             |

## Retrieve Specific Port Forward

The `/api/routers/{router_id}/transient-forwarding/{id}` endpoint allows you to retrieve a specific port forward for the
specified router.

### Endpoint

`GET` `/api/routers/{router_id}/transient-forwarding/{id}`

### Sample Response

```json
{
  "id": "12345678-1234-1234-1234-123456789012",
  "port": 49159,
  "revoked_early": false,
  "allow_only_cidr": "198.51.100.0/24",
  "authorized_at": null,
  "expires_at": "2024-06-22T04:33:29+00:00",
  "expired": false,
  "entry_point": "us-east1.mkcld.io",
  "dst_address": "192.168.88.43",
  "dst_port": 22,
  "time_to_expire": "1 hour from now"
}
```

## Create a Transient Port Forward

The `/api/routers/{router_id}/transient-forwarding` endpoint allows you to create a new transient port forward.

### Endpoint

`POST` `/api/routers/{router_id}/transient-forwarding`

### Creation Object

| Property               | Type    | Description                                                                                                                     |
|------------------------|---------|---------------------------------------------------------------------------------------------------------------------------------|
| `expire_after_minutes` | integer | The duration in minutes for which the port forward should be active (min 10, max 1440).                                         |
| `dst_port`             | integer | The port on the device behind the MikroTik router where the port should be forwarded to. (1-65535)                              |
| `dst_address`          | string  | The IP address that the port is being forwarded to. Must be a valid private (RFC1918) or publicly routed IP.                    |
| `allow_from`           | string  | The IP address or CIDR range from which the connection will be allowed. Must be a publicly routed IP range between /32 and /24. |

### Sample Request

```json
{
  "expire_after_minutes": 120,
  "dst_port": 22,
  "dst_address": "192.168.88.43",
  "allow_from": "198.51.100.0/24"
}
```

### Sample Response

```json
{
  "id": "9c56202d-c388-484d-ac9a-7677f24f1f18",
  "port": 49159,
  "revoked_early": false,
  "allow_only_cidr": "198.51.100.0/24",
  "authorized_at": null,
  "expires_at": "2024-06-22T04:33:29+00:00",
  "expired": false,
  "entry_point": "us-east1.mkcld.io",
  "dst_address": "192.168.88.43",
  "dst_port": 22,
  "time_to_expire": "2 hours from now"
}
```

:::note
In the example above, connections from `198.51.100.0/24` to `us-east1.mkcld.io:49159` are forwarded
to `192.168.88.43:22`.
:::

:::warning
Remember that it may take up to 30 seconds for the configuration to be applied to the router. The port forward will not
be active until the configuration is applied.
:::

## Delete a Transient Port Forward

The `/api/routers/{router_id}/transient-forwarding/{id}` endpoint allows you to delete a specific transient port
forward.

### Endpoint

`DELETE` `/api/routers/{router_id}/transient-forwarding/{id}`

### Response

A successful deletion returns a `204 No Content` response.

## Important Considerations

- **Management Traffic Only**: This feature is intended for management traffic, such as logging into a phone or printer.
  Heavy data transfer is not permitted.
- **TCP Only**: Only TCP traffic is supported.
- **Duration**: The maximum duration for a port forward is 1 day.
- **Default Gateway Requirement**: The device behind the MikroTik router to where traffic is being forwarded must use
  the MikroTik as its default gateway. If not, an extra NAT rule will need to be added programmatically. Look at
  the [asynchronous API](documentation/api-reference/executing-jobs#asynchronous-execution) for guidance on added a
  masquerade rule to overcome this limitation.

## Transient Port Forward Life Cycle

The lifecycle of a transient port forward involves several key steps to ensure proper configuration, usage, and cleanup:

1. **Creation**: When a transient port forward is created, a job is dispatched to the router. The necessary
   configuration is added to the router to establish the port forward.

2. **Usage**: The port forward is active and can be used to access the specified device behind the router. The user must
   connect to the specified entry point and port, which forwards traffic to the destination address and port.

3. **Expiration**: Each transient port forward has a defined expiration time (maximum of 1 day). As the expiration time
   approaches, the time-to-expire property updates accordingly.

4. **Revocation**: If necessary, a transient port forward can be revoked early by issuing a delete request to the API
   endpoint. This will remove the port forward configuration from the router.

5. **Automatic Cleanup**: Upon expiration or revocation, a job is dispatched to the router to remove the port forward
   configuration. This ensures that no stale configurations remain on the router.

By following these steps and using the provided API endpoints, you can effectively manage the lifecycle of transient
port forwards for your MikroTik routers.

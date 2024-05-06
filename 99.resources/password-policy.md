---
title: "MikroCloud Password Policy"
---

## Introduction

Good password hygiene is the cornerstone of security. Where possible, MikroCloud auto-generates passwords for users, but
in some cases, users are required to set their passwords. This document outlines the password policy for MikroCloud.

## Password Requirements

The following are the requirements for a password in MikroCloud:

1. **Minimum Length**: The password must be at least 8 characters long.
2. **Required Characters**: The password must contain at least one uppercase letter, one lowercase letter, one number,
   and one special character.
3. **Password History**: New passwords should not match the last three passwords.

## Password Storage

MikroCloud stores passwords using [one-way hashing](https://en.wikipedia.org/wiki/Bcrypt). This means that passwords
are not stored in plain text. When a user logs in, the password they enter is hashed and compared to the stored hash. If
the hashes match, the authentication workflow continues.

This method ensures that even if a treat actor gains access to the database where passwords are stored, they cannot
reverse-engineer the passwords. 

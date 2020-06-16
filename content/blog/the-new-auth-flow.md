---
title: The New Auth Flow
date: '2020-06-16T10:44:20-03:00'
author: Joel Huggett
---
TinaCMS talks to Github using a proxy, so the authentication token provided by Github is stored as an httpOnly cookie. This stops the client from accessing the token, and that's very good. **But** what it doesn't account for is [CSRF]() attacks, which means any calls to the proxy, so long as that cookie is still there, will succeed, and that's not very good.

A common approach to mitigating this problem is to implement the [Token Synchronization Pattern](). The issue is that this pattern require some form of server-side session storage. That doesn't jive well with the stateless approach of static sites. So, we've introduced a variation that we call the Stateless Token Synchronization Pattern. 

## Upgrading to the new flow

### react-tinacms-github

### next-tinacms-github
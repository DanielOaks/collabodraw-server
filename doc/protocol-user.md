# Collabodraw User Protocol

The User protocol is the primary connection between a Collabodraw interface and the server. It handles login, user state, and creating/removing canvases.

Subprotocol name: `user.cd.pixienop.net`

## Overview

```mermaid
flowchart LR
    Negotiation(Negotiation) --->|as User| Login(Login)
    Login --> BackAndForth(Communication<br>---<br>incoming events<br>outgoing commands)
    Negotiation -->|as Guest| BackAndForth
    BackAndForth --> BackAndForth
```

## Negotiation

...

## Login

...

## Communication

...

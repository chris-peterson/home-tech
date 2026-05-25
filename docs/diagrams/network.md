# Network Topology

End-to-end path from ISP to home devices. Updated as the stack evolves.

```mermaid
%%{ init: { 'look': 'handDrawn' } }%%
flowchart LR
    Internet((Internet))
    Internet --> Quantum[Quantum Fiber 940]
    Quantum --> Gateway[Unifi Gateway]
```

## Ingress

ISP service is [Quantum Fiber 940](https://www.getquantumfiber.com/internet/940-mbps), terminating at a Unifi Internet Gateway.

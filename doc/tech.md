# Technical Design

Technical specifications for Computer Lab CTF

## Infrastructure

Hardware and software systems for hosting the Computer Lab CTF

### Physical

IRL infrastructure

#### Servers

Will purchase two 1U physical machines for hosting challenges. KVM/qemu will
host VMs. Within VMs target applications can be created directly or in containers.
nagios-virt will be used to monitor contest infrastructure. One machine can act
as a failover in the case of hardware failure. We should be prepared to failover
to a remote dedicated server in the case that both machines fail. Hardware
should be tested ahead of time for reliability. If we choose to purchase older
servers this will be even more important - some components may need to be
replaced.

The host machine must be hardened to prevent attacks on the contest. Ideally
it will only be possible to manage the machine from a physical serial port.

We will also need a router and layer-2 switch (we have both). Depending on the
venue other equipment may be necessary to facilitate connectivity. The router
will need to be hardened, ideally we install OpenWRT or similar.

~~If we want to support remote participation we will need a hardware VPN.~~
NO

#### IoT

We are interested in hosting IoT devices on the LAN, including:

* Vaporizers
* PLCs
* Lighting systems (phillips is common)
* IP camera
* Medical devices

### Cloud

Infrastructure we don't control

#### AWS

We will host any non-contest infrastructure in the cloud. This includes CTFd,
landing page, DNS and possibly monitoring / stats systems. This will discourage
attacks against core infrastructure.

## Challenges

Challenges will be small network services. Ideally these can be
language-agnostic. Ideally the services will live in containers for isolation.
Other isolation techniques may be necessary for esoteric services that depend
on platform specific features or legacy operating systems.

**TODO** Challenge framework

## Crypto

We are interested in a game mechanic where the first person to claim a flag can
receive real cryptocurrency. Need to flesh out this idea.

### Ethereum

I feel like Ethereum is a good candidate cryptocurrency since it supports
arbitrary contracts.

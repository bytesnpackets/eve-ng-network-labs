# EVE-NG Network Labs

Hands-on routing and switching labs built in EVE-NG while studying for the CCNA 200-301 and building towards a career in network engineering and security.

Each lab has its own folder with the topology, addressing plan, test results, and notes on what broke and how I fixed it.

## Labs

| # | Lab | Status | Topics |
|---|-----|--------|--------|
| 01 | [Routing and Switching: two-site network](01-routing-and-switching/) | In progress | /30 point-to-point links, L3 switches, static routing, ARP, Wireshark |
| 02 | [IS-IS routing](02-isis-routing/) | In progress | IS-IS neighbours, link-state database |
| 03 | [Two-site OSPF](03-ospf-two-site/) | Planned | OSPF, ECMP, failover and convergence |

## Tools

- EVE-NG (Cisco router and switch images, Linux hosts)
- Wireshark for packet captures
- Reference: *CCNA 200-301 Official Cert Guide*, Volumes 1 and 2

## How each lab is documented

- `README.md`: scenario, goals, what I built, what I learned
- `addressing-plan.md`: IP plan (where relevant)
- `troubleshooting-notes.md`: symptom, how I isolated it, root cause, fix
- `images/`: topology and verification screenshots

## About

> TODO: two or three sentences in my own words (background, what I'm studying, what I'm aiming for).

I write up the problems I hit, not just the working result, because that is where most of the learning happens.

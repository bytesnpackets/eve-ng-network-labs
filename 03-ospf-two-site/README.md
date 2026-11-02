# Lab 03: Two-Site OSPF

**Status:** Planned. Builds on [Lab 01](../01-routing-and-switching/).

## Goal

Replace the per-site static routes with single-area OSPF so Site A (192.168.1.0/24) and Site B (192.168.2.0/24) can reach each other through the ISP router.

## Questions to answer

- How many static routes would the same result have needed, and on which devices?
- Why do SW1 and SW2 end up with two equal-cost paths, and how can I see that in the routing table?
- What happens to traffic when a link in one of the redundant paths goes down, and how long does convergence take?

## Plan

1. Remove the static routes
2. Configure OSPF area 0 on all devices
3. Verify neighbours and the routing table
4. Run a continuous ping between PC1 and PC2 and shut a link to measure convergence
5. Change OSPF cost to influence path choice, and compare traceroutes
6. Later: multi-area OSPF

## Results

> TODO

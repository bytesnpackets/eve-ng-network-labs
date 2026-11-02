# Troubleshooting Notes: Lab 01

Format for each entry: symptom, how I isolated it, root cause, fix, lesson.

---

## 1. Ping works to one address but not another across the same path

**Symptom**
From the ISP router, a static route pointed 10.0.1.0/30 via R1 (10.0.3.1). Pinging 10.0.1.2 (R1) worked, but pinging 10.0.1.1 (SW1) failed.

**How I isolated it**
- Captured traffic in Wireshark on R1 Gi0/0 and SW1 Gi0/1.
- The ICMP echo request reached SW1, but no echo reply was sent.
- Checked SW1's routing table with `show ip route`.

**Root cause**
SW1 had no route back to 10.0.3.0/30, the source network of the ping, so it could not send the reply.

**Fix**
Added a static route on SW1 for 10.0.3.0/30 via R1 (10.0.1.2). Ping then succeeded.

**Lesson**
Ping is two packets. Routing must work in both directions, and the capture showing "request arrives, no reply" points at the return path.

---

## 2. ARP tables did not contain the pinged addresses

**Observation**
After the successful ping, the ARP tables did not show the destination IP I had pinged.

**Explanation**
ARP only resolves addresses on the directly connected link. Each device ARPs for its **next hop**, not for the final destination:
- ISP learns R1's MAC (next hop towards 10.0.1.0/30)
- R1 holds entries for both neighbours: the ISP and SW1
- SW1 learns R1's MAC (next hop for the reply)

**Lesson**
When an ARP entry seems to be missing, ask "what is the next hop for this destination?" rather than "who is the destination?".

---

## Template for new entries

**Symptom**

**How I isolated it**

**Root cause**

**Fix**

**Lesson**

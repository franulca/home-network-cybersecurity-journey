
---
layout: default
title: Step 1 — Inventory & Recon: Seeing the Invisible
---

# Step 1 — Inventory & Recon: Seeing the Invisible

When I moved into my house, I inherited more than just bricks and mortar. The previous owners had left behind parts of a home network setup — racks, a server, some managed switches. Over time, I added my own gear, layer by layer.

But here’s the thing: I’d never actually stopped to map it all out.

That’s where my journey into building a home cybersecurity lab began.

Like many organisations, my “network” had grown organically. No one had a complete picture of what we had, what state it was in, or what would happen if something failed. That’s exactly the kind of risk leaders face every day in enterprise environments.

So I started with Step 1: Asset Management & Recon.

---

## Step 1: Asset Management & Recon

### What I Did
- Listed every device connected to my home network — laptops, phones, NAS, switches, cameras, IoT.
- Built a network map showing how everything connected.
- Added layers of meaning with conditional formatting: health status (green = stable, yellow = unstable, red = offline) and security posture (locked/unlocked icons).

This was my version of a CMDB (Configuration Management Database) — except at home.

### What I Found
The process surfaced some uncomfortable truths:
- **Unstable assets:** a switch in the study cupboard was flaky, often dropping connections.
- **End-of-life devices:** some equipment dated back to 2014, still running default configs.
- **Black box crown jewel:** the UniFi US-48-500W in the garage runs multiple virtual machines, manages segmentation, lighting, firewalls, and storage — but I had no idea when it was last patched or what the disaster recovery plan was.
- **Quick fixes in production:** pfSense had been running on default settings since a past outage. I had brute-forced a fix once by blocking IP addresses from Russian attackers — but that’s not a sustainable or secure strategy.
- **Storage risk:** the NAS showed signs of redundancy failure and hadn’t had updates in years, yet held critical data.
- **Blind spots:** there may be cameras connected that aren’t even switched on.

In other words — exactly the kind of mix you’d expect in an enterprise inherited system.

### Questions That Came Up
As I mapped, bigger questions surfaced:
- **Speed:** Right now my network runs at 1 Gbps. But a chain is only as strong as its weakest link. Which devices and cables are limiting me?
- **Cabling:** Industry standards matter here. Cat5e typically tops out at 1 Gbps, Cat6 can push to 10 Gbps (short runs), and Cat6a reliably delivers 10 Gbps for longer runs. I need to trace my cables and label them properly.
- **Future state:** Next year, my house could be eligible for a 2.5 Gbps upgrade. But my current network wouldn’t make full use of it. Planning ahead now means fewer surprises later.

---

## Looking Through a Framework Lens
One of the things I’m practising is linking hands-on experiences back to established security frameworks. It keeps me honest — am I just tinkering, or am I learning to think like a security leader?

Take the NIST Cybersecurity Framework. The first function, **Identify**, jumped out immediately. Asset management, mapping what’s in play, and knowing its current state — that’s exactly what I was doing by documenting the cables, switches, NAS, and server that make up my home network.  

It reminded me that before you can monitor, detect, or respond, you need a clear baseline.

The CISSP domains also gave me a useful perspective. Security and Risk Management says you can’t protect what you can’t see. That line kept circling back as I looked at the messy cupboard of gear and realised: if something failed tomorrow, no one in the house would know how it all fit together. That visibility gap is a leadership problem as much as it is a technical one.

So yes — I was “just” sketching boxes and cables. But through a framework lens, I was practising the discipline of identification, visibility, and risk awareness — fundamentals that scale whether you’re running a home lab or a large enterprise network.

---

## Personal Reflection
> “My big takeaway was this: a good leader starts with visibility. Before we can protect, we need to see what we have — whether at home or in the enterprise.”

---

## Next Steps
This recon is just the beginning. Here’s where I’m heading next:
- **Switch upgrade:** configure and document the new device replacing the Cisco SG300.
- **Crown jewel review:** get under the hood of the UniFi server — segmentation, patching, DR plan, backups.
- **NAS stabilisation:** address redundancy failures and update an ageing but critical storage system.
- **Camera/automation review:** understand the risks of C-Bus and Clipsal gear running home automation.
- **Future proofing:** prepare for 2.5 Gbps by auditing cables, switches, and endpoints.

---

## Handy Tools & Resources
If you want to try this yourself, here are some tools I found useful in Step 1:
- **Lucidchart** – Easy to map out devices and connections visually. Miro or draw.io are good free alternatives.
- **Excel / Google Sheets** – Great for keeping a lightweight asset register. I used conditional formatting to highlight devices that were unstable, offline, or end-of-life.
- **Speedtest.net & Cable Standards Guide** – Helped me check what speed my setup could actually handle, and whether my cabling (Cat5e, Cat6, Cat6a) was a limiting factor.
- **UniFi Controller Dashboard** – For reviewing how my switches, access points, and VLANs were actually configured.

None of these tools matter as much as the principle: **visibility first, then control**.

---

## Closing
This first step wasn’t about fixing everything. It was about seeing clearly.  
Mapping my home network made the risks, dependencies, and opportunities visible. And that’s the same whether you’re leading a cybersecurity program for 10 devices at home, or 10,000 in a global enterprise.

Visibility comes first. The rest follows.

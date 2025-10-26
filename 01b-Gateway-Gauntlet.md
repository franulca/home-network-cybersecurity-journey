---
title: "The Gateway Gauntlet — When 'Nom Nom' Tried to Eat My Network"
description: "How an over-smart UniFi Cloud Gateway Fibre caused DHCP chaos, and how I rebuilt visibility, control, and stability from the ground up."
date: 2025-10-26
tags: [networking, unifi, troubleshooting, dhcp, home-lab, gateway, fibre]
series: "Home Network Overhaul"
---

## 🌐 The Gateway Gauntlet — When “Nom Nom” Tried to Eat My Network

After *A Bump in the Road*, I was finally starting to feel in control of my home network.  
The switch was behaving, and my cables were finally more organised than spaghetti.  
So naturally, it was time to introduce something new.

Enter the **UniFi Cloud Gateway Fibre** — the sleek, all-in-one device that promised faster routing, unified management, and the gateway to VLANs and security policies.  
I genuinely believed this would be the *easy* part.

Spoiler: it wasn’t.

---

### 🧠 The Plug-and-Play Dream (and Immediate Chaos)

The setup instructions made it sound simple: plug it in, let UniFi’s smart discovery take care of the rest.  
What could possibly go wrong?

Within minutes of connecting it, the Cloud Gateway sprang to life — scanning the network, adopting devices, and generally acting far too confident.  
It didn’t just join the network; it *took* the network.  

We nicknamed it **Nom Nom**, because it went around gobbling up everything it could find.

> Within minutes, devices were flickering in and out of the UniFi console.  
> My network had turned into an all-you-can-eat buffet for Nom Nom.

At first, things *looked* fine — my laptop had Internet access.  
But then my husband’s laptop didn’t.  
My son could access *some* online games, but others refused to connect.  
Even the NAS started acting like it was on a completely different subnet.

Every test contradicted the last one.  
Nom Nom was being “helpful” — but it had no idea what it was disrupting.

---

### ⚔️ The Hidden Battle — pfSense vs Nom Nom

Behind the scenes, my semi–black box server was still running **pfSense**, which had been handling all DHCP and routing duties up until this point.  
Nom Nom, of course, decided it should take over those responsibilities, too.

The result:  
Two routers.  
Both dishing out IP addresses.  
Both insisting they were the rightful boss.

> It was like two teachers trying to mark the same attendance sheet — both convinced the other was wrong.

Devices were hopping subnets.  
DHCP leases were clashing.  
DNS lookups were failing at random.  
One moment everything worked; the next, it all fell apart.

Eventually, I couldn’t access the Internet at all.  
Nom Nom had eaten too much.

---

### 🧭 Hitting Pause — Redefining What Success Meant

With the chaos unfolding and no stable Internet connection, I had to wait for my last remaining piece of rescue tech — an *ancient laptop* — to charge.  
It was slow, heavy, and loud… but crucially, it had a **LAN port**.  

While waiting, I took the opportunity to pause and think.  
Not just “how do I fix this?” but “what *am I actually trying to achieve* with this setup?”

That reset moment became the turning point.  

Here were my **real goals**:

- ✅ See *detailed configuration options* in the UniFi console — not just a vague “setup in progress” screen.  
- ✅ Access the **UniFi cameras** I’d seen around the house (a project for a later post).  
- ✅ View *every device* connected to the network, clearly named and grouped.  
- ✅ Get *visibility into network traffic* — who’s doing what.  
- ✅ Achieve *2.5 Gbps* speeds where supported.  
- ✅ Create *new VLANs and firewall policies* with confidence.  

This wasn’t just about getting the Internet back.  
It was about building **transparency and control**.

---

### 🧰 Going Offline to Regain Control

When you can’t trust automation, the only option is to go manual.

Once the old laptop finally powered up, I connected it directly to the Cloud Gateway — no switch, no pfSense, no distractions.  
It became my tiny, isolated testing ground.

I manually configured the laptop’s IP to avoid conflicts with the old pfSense range, defined a narrow DHCP scope for the Gateway, and started fresh.  

For the first time, I could *see* what the Gateway was actually doing — and more importantly, what it shouldn’t be doing.

> Sometimes the best debugging tool isn’t new tech — it’s old hardware that still has a LAN port.

---

### ⚙️ Slowly Taming Nom Nom

With isolation came clarity.  
Step by step, I started taking control back:

- Disabled DHCP on pfSense, but only after confirming the Gateway’s configuration.  
- Assigned static IPs for core devices to stabilise routing.  
- Re-adopted the switch into the UniFi console.  
- Verified that each VLAN and subnet behaved predictably.  
- Watched, with cautious optimism, as topology maps started making sense again.

Nom Nom was no longer roaming freely.  
It was still smart — but *contained*, working within rules I defined.  

The best part?  
By the end, every goal from my earlier list was achieved.

---

### 💡 Lessons Learned

- **Smart defaults aren’t always smart.**  
  Automation is great until it makes assumptions your network can’t handle.  
- **Two DHCP servers = instant chaos.**  
  Pick one. Guard it carefully.  
- **Offline testing saves sanity.**  
  A single laptop and cable can isolate problems faster than any “wizard.”  
- **Define success before you chase it.**  
  Clarity turns frustration into focus.  
- **Adopt incrementally, not automatically.**  
  One device at a time keeps the system understandable.

> Nom Nom taught me that automation without visibility is just chaos with better marketing.

---

### 🚀 What’s Next — From Control to Segmentation

Now that the Cloud Gateway is stable and behaving, I can finally start designing proper VLANs — isolating work, IoT, media, and management zones.  
Each will have its own security rules, traffic priorities, and visibility within UniFi.

And those UniFi cameras that started this whole curiosity?  
They deserve their own deep dive — that’ll be the next chapter.

---

*Part of the “Home Network Overhaul” series.*  
If you missed the first post, check out [**A Bump in the Road**](../a-bump-in-the-road/) to see where this all began.

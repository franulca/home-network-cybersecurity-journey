# First Bump in the Road: Which Switch to Switch?

Every great quest hits its first real bump in the road. For me, it wasn’t a dragon or a rogue firewall — it was a humble, aging Cisco SG300 switch at the heart of my home theatre network. 
Suddenly, family movie nights and gaming marathons were haunted by the dreaded “Ethernet not connected” message. But the deeper I looked, the clearer it became: this wasn’t just a quirky fault. The SG300 had reached end-of-life, no longer supported with updates or security fixes, and was now unstable at the worst possible time.

The culprit? A switch that couldn’t decide if it wanted to stay online or not. Cue the question that framed my whole troubleshooting adventure: which switch to switch?

---

## Background

The Cisco SG300 is a small-business managed switch, well-known for its reliability in enterprise-lite settings. It supports advanced features like VLANs and even Layer 3 routing — though in my case, that Layer 3 capability was largely redundant, since my UniFi 48-port gigabit switch earlier in the network already handled those duties.
For context, here’s where it sat in my setup:

Internet ➝ UniFi 48-port 500W managed gigabit switch ➝ Server (with multiple VMs) ➝ Cisco SG300 ➝ Home theatre stack (amplifier, PS5, Nintendo Switch, Xbox, NVIDIA Shield).
[Insert network diagram here]

On paper, the SG300 was plenty capable. In practice, it became the weak link.

## Problem Discovery
The issues first crept in as intermittent slowdowns and mysterious “Ethernet not connected” messages on devices in the theatre setup. What looked like small annoyances at first turned into network-wide disruption:

- Ports dropping out or restarting after the slightest bump to a cable.

- Latency spikes noticeable during gaming.

- General instability undermining the entire stack downstream.

It wasn’t just inconvenient — it was destabilising. And given the SG300’s central role in that branch of the network, it became clear that the switch itself was the hazard.

## Security and End-of-Life Considerations
The instability was enough on its own to justify replacement, but there was a bigger red flag: the SG300 line officially reached End of Sale in September 2019 and End of Life in September 2023. With no more firmware or security patches, the device was effectively frozen in time.
That matters. An unstable switch that’s also out of support introduces risks:
- No security fixes for vulnerabilities.
  
- Incompatibility with newer devices or protocols.
  
- Reduced resilience — once something breaks, it stays broken.

For a network I’m trying to harden against both performance hiccups and security gaps, keeping it around was a liability.

## Troubleshooting
I kept it simple: hands-on port testing.
Bumping cables connected to the SG300 reliably caused ports to drop and the switch to stumble through a gradual restart. I even caught it on video — a clear sign that this wasn’t just config gremlins or firmware weirdness. It was hardware failing in real time.

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
  <iframe 
    src="https://www.youtube.com/embed/7qdy1CmuSnI?si=0UL0z2lMdwkBkfXM" 
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    referrerpolicy="strict-origin-when-cross-origin"
    allowfullscreen
    style="position: absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>




At that point, no amount of VLAN tweaking or firmware flashing was going to resurrect it.

## Decision Points
Once the SG300 was officially in the “retire me” bucket, I weighed a few options:
- Replace with another Cisco SG300 (or similar enterprise switch)
  - Pros: Familiar, enterprise features I already knew.
  - Cons: Expensive, already end-of-life, risk of running into the same instability again.

- Step into the full UniFi ecosystem
  - Pros: A rack-mountable UniFi switch would plug me into modern centralised management — VLAN orchestration, monitoring, and seamless integration with the UniFi Controller. It’s a powerful way to standardise and future-proof the whole network.
  - Cons: Overkill for a home theatre branch. It adds cost, complexity, and features I don’t actually need here.

- Scale down to something simpler: the Ubiquiti UniFi Flex 8 Port 2.5Gbe PoE++ Switch
  - Pros: Compact, fanless, quiet, and reliable — with enough 2.5G speed and ports to cover the theatre stack. Still part of the UniFi family, but right-sized for an edge role without dragging me into a full ecosystem build-out just yet. PoE is there if I ever need it, but all my devices have their own power.
  - Cons: Fewer bells and whistles than the full UniFi gear — but in this part of the network, those bells don’t ring anyway.

## The Decision
After a round of port testing (and one very telling video of the SG300 dropping out when a cable was nudged), the decision became clear: retire the Cisco and bring in the UniFi Flex 2.5G. It gave me the right balance of reliability, simplicity, and future-proofing without overcomplicating my setup — at least for now.


And with that, the question of which switch to switch was answered.

---

## Conclusion
The bump in the road was more than a minor hiccup — it was a clear signal that my network’s foundation needed attention. Retiring the Cisco SG300 in favour of the UniFi Flex 2.5G wasn’t just a hardware swap; it was a deliberate choice for the right balance of reliability, simplicity, and future-proofing without overcomplicating my setup — at least for now.
The question of which switch to switch was answered.

And just like that, family game nights and movie marathons were rescued from the brink of Ethernet chaos.

**Next step**: fire up Ghosts of Yatoi and savour the victory.

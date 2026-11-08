# Minecraft Server Hosting: How Much RAM You Need, What a Year Really Costs, and When Bare Metal Starts to Make Sense

Two numbers decide your bill: peak concurrent players and how many mods load at boot. A vanilla server for six friends runs fine on 4 GB at roughly $10 a month. Spin Servers, the host this page points to, sells a different product: bare-metal dedicated servers, with the cheapest pre-built configuration listed at **$79/mo for 32 GB RAM, 4 vCPU and 1 TB NVMe**. That box is the right buy for a 40-player modded community, a network of several instances, or anyone who wants root on the machine and 30 TB of transfer.

It is the wrong buy for almost everyone else. Below you get the four configurations currently listed, the RAM sizing rules that decide whether a $10 plan or a $79 machine fits, a twelve-month cost comparison across the hosts people actually shortlist, and the fine print that never makes it onto a pricing page.

> **Quick pick:** the entry Spin Servers box is the Xeon E3-1280 v5 in Dallas or San Jose: 32 GB RAM, 4 dedicated cores, 1 TB NVMe, 30 TB bandwidth, $79/mo. Choose it when your bottleneck is CPU isolation or instance count, not when you just need more gigabytes.
> 👉 [Check the $79/mo Xeon E3-1280 v5 configuration](https://bit.ly/Spinservers)

## What Spin Servers actually sells

Spin Servers does not list a managed Minecraft plan with a one-click Paper or Forge installer. Its store sells pre-built instant dedicated servers: whole machines, root access, no management layer. You install the Java runtime and the server jar yourself, or run a control panel on top of the box. If you have never opened a terminal, this is not the product to start with, and no amount of RAM changes that.

## The four configurations currently listed

| Configuration | CPU / RAM | Storage | Price (USD) | Order |
| --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5, Dallas | 4 vCPU / 32 GB | 1 TB NVMe | $79/mo | [View plan](https://bit.ly/Spinservers) |
| Intel Xeon E3-1280 v5, San Jose | 4 vCPU / 32 GB | 1 TB NVMe | $79/mo | [View plan](https://bit.ly/Spinservers) |
| Dual Intel Xeon Gold 6148, Dallas | 40 vCPU / 256 GB | 3.84 TB SSD | $235/mo | [View plan](https://bit.ly/Spinservers) |
| Dual Intel Xeon Platinum 8173M, Dallas | 56 vCPU / 512 GB | 7.68 TB SSD | $390/mo | [View plan](https://bit.ly/Spinservers) |

What comes with every one of them:

- 30 TB of bandwidth per month
- Root access, unmanaged
- 99.99% uptime SLA
- Support by ticket, phone and email
- Two US locations: Dallas and San Jose
- Renewal pricing and a money-back window are not published on the listing

Those last two points matter more than the spec sheet. Before you pay for an annual term anywhere, ask sales in writing what the renewal rate is and whether there is a refund period. A $79 starting price tells you nothing about month thirteen.

The 256 GB and 512 GB machines are not Minecraft purchases. They make sense for a hosting reseller or someone running a dozen game servers side by side. For a single Minecraft world, the E3-1280 v5 is the only realistic entry point, and its limit is four cores: enough for one heavily modded server or three or four small vanilla instances, not enough for both at once.

## How much RAM a Minecraft server needs

Host Havoc publishes the clearest player-count mapping in the category, split by vanilla and modded:

| RAM | Vanilla players | Modded players |
| --- | --- | --- |
| 6 GB | 35–50 | 15–25 |
| 8 GB | 50–75 | 25–40 |
| 12 GB | 75–150 | 40–60 |
| 16 GB | 250+ | 60–80 |
| 24 GB | 250+ | 80–120 |

Read across a row and the pattern is obvious: for the same memory, a modded server carries roughly 40–50% of the vanilla player count. Host Havoc also states the floor directly: at least 4 GB for any modpack, 8 GB or more for kitchen-sink packs.

The reason is where the memory goes. Players connect and disconnect and cost relatively little while they are online. A modpack registers thousands of blocks, items and entity types at startup, adds dimensions that each keep their own chunk and world-generation data, and runs per-tick logic from machines, mobs and pipes whether or not anyone is nearby. That footprint is there before the first player joins, which is why a 2 GB plan that handles ten vanilla players fine will fall over on All The Mods with two people online. Host Havoc puts its 1 GB and 2 GB tiers down as "Modded: Not Recommended" for exactly this reason.

CPU is the other half, and it is where budget hosts flatten out. Sparked Host prices memory almost linearly at about $1 per GB per month, from 1 GB at $1 up to 22 GB at $22, but its top plan still only lists 5 vCPU. You can buy 22 GB of RAM and very little processing power to tick the world with. Tick work is largely single-threaded, which is why hosts advertise single-thread benchmarks at all. Falix publishes a relative CPU table on its Minecraft page (Apex Hosting 91%, BisectHosting 90%, Bloom Host 74%, Shockbyte 73%) built from PassMark single-thread scores, and it is worth knowing that this is Falix's own comparison sheet rather than an independent benchmark. The direction it points in is still correct: for a 30-player modded server, one fast core beats four slow ones.

## What twelve months actually costs

Four hosts, four currencies, three billing cycles. The headline number is not the annual cost.

| Host | Plan | Listed price | Billing | 12 months |
| --- | --- | --- | --- | --- |
| Modrinth Hosting | Small, 4 GB | $10/mo | Billed quarterly | $120 |
| Sparked Host | 8 GB | $8/mo | Monthly | $96 |
| Host Havoc | IRON, 6 GB | £16.53/mo | Monthly | £198.36 |
| Falix | Starter, 4 GB | €12/mo | Monthly | €144 |
| Spin Servers | Xeon E3-1280 v5, 32 GB | $79/mo | Monthly | $948 |

Modrinth's $10, $15 and $20 tiers are quarterly-billed rates, which is how the "save 16%" line works: you pay for three months up front. Multiply by four and the real annual figures are $120, $180 and $240. Host Havoc prices in pounds, Falix in euros, everyone else in dollars, so converting before comparing is your job, not the pricing page's.

Within one currency, the gap is stark. Sparked Host's 8 GB plan costs $96 a year; the Spin Servers entry box costs $948. Per gigabyte of RAM, Spin works out to about $2.47 per GB per month against roughly $1 per GB at Sparked. You are not paying the premium for memory. You are paying for whole cores instead of vCPU slices, 1 TB of NVMe instead of 30 GB, 30 TB of transfer, and root access to the machine. If your only complaint is "the server needs more RAM", the dedicated box is five to eight times the price for a problem a $12 plan solves.

The honest comparison is against the top of the managed range. Host Havoc's 24 GB OBSIDIAN plan is £66.12/mo, or £793.44 a year, and it explicitly does not oversell its nodes. Whether $948 for 32 GB on dedicated hardware beats that depends on whether your server is short of memory or short of CPU, and only your own tick timings answer that.

## Fine print that decides whether a cheap plan is usable

- **Sparked Host** refunds within the first 24 hours only, and only if the provider fails to fix the issue. That is a repair guarantee, not a change-of-mind window.
- **1up-servers** free tier gives 2 GB RAM, 4 player slots, 6 GB disk, no backups, and 3 hours of runtime per day capped at 30 hours a month. An idle server stops after 30 minutes. Its paid tiers start at €3/mo for 6 slots and €5/mo for 4 GB.
- **Host Havoc** offers a 72-hour money-back guarantee, but its 1 GB and 2 GB plans carry the "Modded: Not Recommended" label in writing.
- **Sparked Host add-ons** rewrite the bill on a small plan: a dedicated IP is +$4/mo, dual Java and Bedrock ports +$6.75/mo, and full server management +$20/mo. On a $1 plan those are 4× to 20× the base price.
- **Spin Servers** publishes neither a refund window nor a renewal price. Get both in writing before you commit, because a dedicated server is a bigger cheque than any managed plan on this page.

👉 [See the full Spin Servers dedicated server listings and current pricing](https://bit.ly/Spinservers)

## Ports and versions: why a fresh server says "can't connect"

On a managed host the panel handles this. On a bare-metal box you do, and these are the current failure points:

- Java Edition listens on TCP 25565. Bedrock uses 19132, but the transport changed with Bedrock 26.50: dedicated servers now default to NetherNet, which does a TCP handshake on 19132 and then runs gameplay over UDP ports negotiated per player. Either forward TCP 19132 plus your configured UDP range, or set `transport=raknet` in `server.properties` and forward classic UDP 19132.
- Java release 26.3 requires a Java 25 runtime. Installing Java 21 and wondering why the jar refuses to start is the single most common self-managed mistake right now.
- Geyser, the plugin that lets Bedrock clients join a Java server, officially supports Java 26.2 with Bedrock 26.30 to 26.52. 1up-servers tested Geyser on Paper 26.2 (it loads) and on 26.3 (it fails), which is why their panel blocks switching above 26.2. If you run crossplay on your own machine, pick your Java version around Geyser, not the other way around.

## Which one to buy

- **1–10 friends, vanilla or a handful of plugins:** 4 GB managed. Modrinth Small at $10/mo billed quarterly ($120/yr) or Sparked's 4 GB at $4/mo. A dedicated server is wasted money here.
- **15–40 players, or a kitchen-sink modpack:** 8–12 GB with real CPU headroom. Modrinth Large at $20/mo ($240/yr) bursts to 8 CPUs; Host Havoc GOLD at £33.06/mo publishes 75–150 vanilla players and 40–60 modded.
- **40+ players on a heavy pack, several instances, or reselling:** the $79/mo Spin Servers box. Four dedicated cores and 32 GB will hold a large modded world plus a couple of small vanilla servers, and nobody else's busy node affects your tick rate.
- **You need root for other reasons:** multiple game servers, custom backups, a proxy network. Managed Minecraft hosts do not sell that; dedicated hardware does.

Two things to confirm before any checkout: for Spin Servers, the renewal rate and refund terms, since neither is published; and for any managed host, whether the plan's CPU allocation survives your modpack at peak hours, because RAM is the number they advertise and CPU is the number that causes lag.

👉 [Start with the $79/mo entry box in Dallas or San Jose](https://bit.ly/Spinservers)

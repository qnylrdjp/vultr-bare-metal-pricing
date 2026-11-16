# Buy Dedicated Server: What It Really Costs, Which Plan Fits, and Where the Renewal Price Catches You (Full Vultr Bare Metal Table)

Renting a physical server runs from roughly €25 a month at the bottom of the market to €600+ for high-core-count hardware, with most usable single-socket machines landing between €100 and €200 a month. Vultr's bare metal line starts at **$120/mo** for a 4-core Intel E3-1270 with 32 GB RAM, billed hourly with no term contract, and tops out at **$1,450/mo** for a 32-core EPYC with 768 GB.

Three things move your real monthly cost more than the CPU badge: whether the box is managed, how long you're locked in, and whether the advertised price survives month thirteen. This article works through all three, then shows every bare metal configuration Vultr currently lists so you can match a plan to a workload instead of guessing.

## The short version

> **Cheapest physical machine at Vultr:** Intel E3-1270, 4 cores, 32 GB RAM, 2 × 240 GB SSD, 10 Gbps port, **$120/mo**, hourly billing.
> **The plan most people should start on:** Intel E-2286G (6 cores, 32 GB, 2 × 960 GB SSD, **$185/mo**) if you want SATA capacity, or AMD EPYC 4245P (6 cores, 32 GB, 2 × 960 GB NVMe, **$295/mo**) if disk speed is the bottleneck.
> **Skip unless you're consolidating:** the 24-core and 32-core EPYC plans from $725 to $1,450/mo. One app on one of those is a waste of four figures a year.

👉 [See Vultr's bare metal plans and current monthly prices](https://www.vultr.com/products/bare-metal/?ref=9738262-9J)

## Every Vultr bare metal plan in one table

All eleven configurations ship with a 10 Gbps port and are self-managed. Prices are monthly; hourly billing is also available, so you are not signing a year away to test a machine.

| Plan (processor) | Cores | RAM | Storage | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Intel E3-1270 | 4 | 32 GB | 2 × 240 GB SSD | $120/mo | [ E3-1270](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| Intel E-2286G | 6 | 32 GB | 2 × 960 GB SSD | $185/mo | [ E-2286G](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 4245P | 6 | 32 GB | 2 × 960 GB NVMe | $295/mo | [ EPYC 4245P](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| Intel E-2288G | 8 | 128 GB | 2 × 1.92 TB NVMe | $350/mo | [ E-2288G](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| Intel E-2388G | 8 | 128 GB | 2 × 1.92 TB NVMe | $350/mo | [ E-2388G](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 4345P (64 GB) | 8 | 64 GB | 2 × 1.945 TB NVMe | $365/mo | [ EPYC 4345P 64 GB](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 4345P (123 GB) | 8 | 123 GB | 2 × 1.945 TB NVMe | $395/mo | [ EPYC 4345P 123 GB](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 7443P | 24 | 256 GB | 2 × 480 GB SSD | $725/mo | [ EPYC 7443P](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 9254 | 24 | 384 GB | 2 × 480 GB SSD | $825/mo | [ EPYC 9254](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 9255 | 24 | 384 GB | 2 × 480 GB NVMe | $995/mo | [ EPYC 9255](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |
| AMD EPYC 9354P | 32 | 768 GB | 2 × 480 GB SSD | $1,450/mo | [ EPYC 9354P](https://www.vultr.com/products/bare-metal/?ref=9738262-9J) |

Two things worth knowing before you pick a row. First, there is no setup fee, and the renewal price matches the signup price on every plan listed, so the number in the table is the number you keep paying. Second, Vultr's bare metal listings show no custom builds and no self-serve IPMI or KVM console, which means you deploy from the offered operating system images rather than mounting your own ISO. If you need to install a custom image through IPMI, that's the point where a provider like HOSTKEY does something Vultr doesn't.

Availability differs by region. Not every configuration sits in every location Vultr operates, so the plan list you see after choosing a region is the authoritative one.

## "Dedicated" means two different things, and one of them is a virtual machine

Search results mix two products under the same phrase, and the price gap between them is roughly tenfold.

A true bare metal server gives you the entire physical machine. OVHcloud defines it as a machine that allocates all of its hardware resources to the user, with no virtualisation layer consuming CPU cycles, and contrasts that directly with a virtual server that hands a slice of resources to the hypervisor. Its servers list real CPU models, dual physical network cards, hardware RAID options, and per-machine backup space.

A root server gives you dedicated resources on a shared virtualisation platform. netcup says this in its own words: "Our root servers are not classic bare metal servers, but a modern alternative: you get dedicated resources such as CPU, RAM, and storage that are available only to you." Those plans start at €12.93/mo excluding VAT (€14.87 including 19% VAT) on a 12-month contract, which is why they dominate the cheap end of the results.

Here's the check that settles it in ten seconds. If the page names a specific processor model, RAM slots, a RAID controller and an IPMI interface, it's a physical server. If it talks about "dedicated vCores" and "dedicated resources" while showing a vCPU count, it's virtual. Nothing wrong with either, but you cannot price them against each other.

## The first-year price is not the price

Promotional pricing usually has an expiry date printed somewhere small.

Contabo's AMD Turin 32-core plan shows €359.10/mo against a crossed-out €399.00, and the page states plainly that this applies "for the first 12 months." The 64-core version is €629.10/mo against €699.00, same condition. That's a real saving of €478.80 over the first year on the 32-core box, followed by a €39.90/mo step up in year two. Budget for the crossed-out figure, not the bold one.

Liquid Web runs a different structure: its Intel 6226R configuration (16 cores, 64 GB, 2 × 960 GB SSD RAID-1, 10 TB bandwidth) is listed at $167.50/mo with "50% off 2 mos." Two months later the discount ends. Note also that the same processor and specification appears at several different prices on that page depending on configuration and contract, so treat any single number as one quote among many rather than the standard rate.

Vultr takes the opposite approach: no promotional rate that later resets, no annual commitment, hourly billing. You pay list price from hour one and keep paying it. For a two-year horizon the $120 plan costs $2,880 with no surprises; the trade-off is that you also get no discount for committing and, per Vultr's published terms, no money-back window. You can stop billing at any time, but you won't get a refund for time already served.

👉 [Check Vultr's current bare metal rates, billed hourly with no term contract](https://www.vultr.com/products/bare-metal/?ref=9738262-9J)

## What "unlimited traffic" actually permits

Three providers describe unlimited traffic three different ways, and none of them means "send as much as you like."

OVHcloud says its dedicated servers are unmetered by default, with an explicit exception for its Asia-Pacific data centres, and reserves the right to limit outbound public bandwidth to as much as 50% when your usage affects other customers. Contabo states that incoming traffic is unlimited and unmetered, then adds that if usage is exceptionally high or disruptive it reserves the right to throttle servers at its own discretion. HOSTKEY is the most literal: inbound traffic is free under fair use, and outbound limits and rates depend on the traffic plan you buy.

Vultr publishes a hard number instead of a policy. The entry bare metal configuration lists 5 TB of bandwidth, and additional outbound traffic is billed at $0.01/GB, which is $10 per extra terabyte. For a site serving 20 TB a month that's $150 in overage on a $120 server, so run the arithmetic on your actual egress before comparing headline prices.

## Managed or unmanaged is a bigger line item than the CPU

Liquid Web's dedicated servers include 99.99% uptime, built-in DDoS protection, 24/7 expert management and data centres assessed for HIPAA, PCI-DSS and GDPR, plus ServerSecure hardening and a choice of control panels. You are paying for people, not just silicon, and that's why a 16-core machine with 64 GB lists in the hundreds per month.

HOSTKEY goes the other way: every server is unmanaged and management is a separate paid service. You get IPMI access, a replacement server pool, component swap-outs and a first support response within 15 minutes, but you own the operating system, the patching and the 3 a.m. failures.

Vultr sits in the unmanaged camp too. Support runs through tickets, and DDoS protection is not bundled: it's a $10/mo add-on. Automatic backups add 20% to the server price.

The judgment call is simple. If nobody on your side can patch a kernel and read a log at midnight, add the management cost to the cheap unmanaged quote before comparing. One unplanned multi-hour outage usually costs more than a year of the difference.

👉 [Start with Vultr's $120/mo bare metal and add DDoS protection for $10/mo](https://www.vultr.com/products/bare-metal/?ref=9738262-9J)

## Which configuration fits which job

**A single site or app with steady traffic.** The 6-core bracket is where the value sits: $185/mo for the E-2286G with 2 × 960 GB SSD, or $295/mo for the EPYC 4245P with NVMe if your database is I/O bound. Going below 6 cores to save $65 rarely pays off once you add a database and a queue.

**Multiple services on one box.** Eight cores with 128 GB RAM at $350/mo (E-2288G or E-2388G, both with 2 × 1.92 TB NVMe) lets you run several VMs or containers plus a database without fighting for memory. The $365 and $395 EPYC 4345P variants trade RAM capacity for newer silicon, which matters if you're CPU-bound rather than memory-bound.

**Virtualisation hosts, game servers with many slots, analytics.** The 24-core EPYC 7443P at $725/mo with 256 GB is the entry point to that class. Above it, $825 and $995 buy 384 GB of RAM, and $1,450 buys 32 cores with 768 GB. Only jump here if a consolidation exercise replaces three or more smaller servers.

**Not sure you need a physical machine at all.** You probably don't. Cloud compute instances start at $2.50/mo (IPv6-only; $3.50 with IPv4), and Vultr's Optimized Cloud Compute line with dedicated CPU starts at $28/mo. A blog, a staging environment or a low-traffic API belongs there, not on a $120 server.

## Six things to confirm before you pay

1. **Contract length and notice period.** Contabo's minimum initial term is one month, with four weeks' notice for postpaid accounts. netcup's root servers run on a 12-month contract. Vultr bills hourly with no term.
2. **Refund window.** netcup offers a 30-day money-back guarantee. Vultr's bare metal listings show no refund period, so test on hourly billing before you commit to a long-running deployment.
3. **Whether tax is included.** netcup quotes €12.93/mo excluding VAT and €14.87 including 19% VAT. A 19% difference on a €300 server is €57 a month.
4. **Whether the delivery time is contractual.** OVHcloud states its deployment times are for information purposes only and do not constitute a contractual condition. Plan migrations around that.
5. **What the DDoS protection actually covers.** HOSTKEY's free basic protection applies in Europe and covers specific flood types; HOSTKEY outbound traffic is billed separately. Vultr charges $10/mo for its DDoS add-on.
6. **Backup costs.** OVHcloud includes 500 GB of backup space per server, expandable to 2.25 TB or 10 TB. Vultr charges an extra 20% of the server price for automatic backups, and snapshots run $0.05/GB/month.

## The decision rule

If you need maximum control for years and have the ops staff, buy hardware. If you need a physical machine without a contract and want to be running within the hour, rent hourly: the 6-core Vultr plans at $185 and $295 cover most production workloads, the 8-core 128 GB pair at $350 covers consolidation, and anything above $725 should replace at least three servers to justify itself. If you have no one to manage the box, price the managed option first and treat the unmanaged quote as incomplete.

One last thing to check at signup: the link below carries Vultr's new-account credit promotion advertised at $300. Eligibility, expiry and which products the credit applies to are set in the terms shown during registration, so read them before you deploy rather than after.

👉 [Compare Vultr bare metal configurations and claim the new-account credit](https://bit.ly/VuLtr)

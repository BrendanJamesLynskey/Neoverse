# ▣ Arm Neoverse Presentation Series

Interactive slide decks covering Arm's **Neoverse** infrastructure and server-class CPU family — from the first Neoverse N1 (Graviton 2, 2019) through the current **N3 / V3** generations, the **CMN mesh interconnects** that glue them together, the **Server Base System Architecture (SBSA)** platform contract, and the **hyperscaler ecosystem** that has made Arm servers a ~50 % share of AWS compute.

Designed as interview preparation for server-silicon, infrastructure, and performance engineers targeting Arm, AWS, Ampere, NVIDIA, Microsoft, and other Neoverse customers.

## ▶ [Open the Series Landing Page](https://brendanjameslynskey.github.io/Neoverse/)

> **Setup:** Enable GitHub Pages (Settings → Pages → Deploy from `main` branch, `/ (root)` directory).
>
> Alternatively, open `index.html` locally in any browser — all presentations work offline after first load.

---

## Presentations

| # | Topic | Slides | Status |
|---|-------|--------|--------|
| 01 | History &amp; Product Lines — N, V, E Families | 16 | ✅ Complete |
| 02 | Neoverse Microarchitecture &amp; Core Details | 17 | ✅ Complete |
| 03 | CMN Mesh Interconnect — CMN-600 / 650 / 700 / S3 | 16 | ✅ Complete |
| 04 | SBSA, SystemReady &amp; the Platform Contract | 15 | ✅ Complete |
| 05 | The Ecosystem — Graviton, Ampere, Grace, Cobalt, A64FX | 16 | ✅ Complete |

---

## Presentation 01: History &amp; Product Lines

16 slides on the arc from Cortex-A72 servers (Marvell ThunderX, Ampere eMAG) through the launch of **Neoverse** as a dedicated brand in October 2018 — with the announcement of three roadmaps (Cosmos → Ares → Zeus → Poseidon). Covers **N1** (2019 — the Cortex-A76 re-characterised for servers, shipped in **AWS Graviton 2**), **V1** (2021 — first with 2 × 256-bit SVE, Graviton 3, SiPearl Rhea), **E1** (2020 — edge/NIC class), **N2** (2022 — first v9-A Neoverse, SVE2, Graviton 4 early variants, Ampere Altra successor), **V2** (2022 — X3-derived, NVIDIA Grace), **N3 / V3** (2024 — SVE2 + bf16 / INT8, CMN S3 mesh, Realms/CCA in hardware).

## Presentation 02: Neoverse Microarchitecture

17 slides on the core internals that differ from desktop-Cortex — bigger L1/L2, larger ROBs (~384 entries in V2), deeper OoO issue, wider SIMD (V1 has 2 × 256-bit SVE FP pipelines, V2 has 4 × 128-bit), dual-thread (SMT2) in V1/V2, private L2 sizes up to 2 MB, large LLC (SLC in the CMN mesh). Also covers the RAS (Reliability/Availability/Serviceability) features, ECC, lockstep, and the <em>why</em> Neoverse cores trade single-thread IPC for throughput + socket density.

## Presentation 03: CMN Mesh Interconnect

16 slides on the <strong>Coherent Mesh Network (CMN)</strong> family — <strong>CMN-600</strong> (Ares platform, up to 8×8 mesh, 128 coherent nodes), <strong>CMN-650</strong> (CCIX + PCIe Gen 4), <strong>CMN-700</strong> (Zeus platform, up to 12×12 mesh, 512 CHI-E cache lines, CCIX 1.1 + CXL 2.0 sideband), <strong>CMN S3</strong> (Poseidon, 2024 — unified on-die + chiplet topology, CHI-E2, UCIe and CXL 3.0). Walks through mesh node types — <strong>RN-F</strong> (CPU clusters), <strong>HN-F</strong> (home nodes / SLC slices), <strong>SN-F</strong> (DRAM memory nodes), <strong>RN-I</strong> (IO bridges), <strong>MN</strong> (misc interconnect services) — and explains how a snoop, a home-node response, a DRAM access, and a PCIe DMA all flow through the mesh.

## Presentation 04: SBSA, SystemReady &amp; the Platform Contract

15 slides on <strong>why</strong> a Neoverse platform is more than just a CPU core. Covers the <strong>Server Base System Architecture (SBSA)</strong> levels (3 / 4 / 5 / 6 / 7) that progressively mandate GICv3, PMU, EL3, SMMUv3, PCIe, CCA, and more. Covers <strong>SBBR</strong> (boot requirements), <strong>BSA</strong> (Base System Architecture — an SBSA superset for all Arm platforms), <strong>SystemReady</strong> program tiers (SR, ES, IR, LS), and how a distro-grade Linux (RHEL, Ubuntu) boots on any SystemReady-SR certified machine without vendor patches — the same contract x86 has had via UEFI / ACPI for decades.

## Presentation 05: The Ecosystem

16 slides covering every major Arm server SoC:
<strong>AWS Graviton 1 / 2 / 3 / 3E / 4</strong> (Annapurna Labs → Nitro, Graviton 4 = 96 × N2, launched 2024),
<strong>Ampere Altra / Altra Max / AmpereOne</strong> (N1 → custom-core Oryon successor),
<strong>NVIDIA Grace / Grace Hopper / Grace Blackwell</strong> (72 × V2, 480 GB LPDDR5X, NVLink-C2C),
<strong>Microsoft Cobalt 100</strong> (N2 × 128, Azure datacentre silicon, 2024),
<strong>SiPearl Rhea1</strong> (V1-based European HPC, Jupiter exascale system),
<strong>Fujitsu A64FX / MONAKA</strong> (custom Armv8-A / v9-A with SVE, Fugaku &amp; its successor),
<strong>Alibaba Yitian 710</strong> (N2 × 128, Alibaba Cloud).
Closes with the 2024 &quot;Arm Total Design&quot; program that gives customers reference CSS (Compute Subsystem) platforms — pre-integrated Neoverse + CMN + CoreSight + GIC + SMMU, ready for chiplet integration.

---

## Technical details

- **Framework:** [Reveal.js 4.6.1](https://revealjs.com) from CDN
- **Fonts:** Playfair Display (headings), DM Sans (body), JetBrains Mono (code)
- **Offline:** works after first load (fonts &amp; Reveal.js cached by the browser)
- **Navigation:** `→` / `←` for slides, `Esc` for overview, `F` for fullscreen, `S` for speaker notes

## Related repositories

- [Hardware](https://github.com/BrendanJamesLynskey/Hardware) — parent hub
- [Arm Cortex-A Presentation Series](https://github.com/BrendanJamesLynskey/Cortex_A) — the mobile A-profile cores that Neoverse derives from
- [Arm Cortex-M Presentation Series](https://github.com/BrendanJamesLynskey/Cortex_M) — the M-profile sibling
- [Arm System IP Presentation Series](https://github.com/BrendanJamesLynskey/Arm_System_IP) — GIC, SMMU, DSU, MPAM
- [Arm AMBA Presentation Series](https://github.com/BrendanJamesLynskey/AMBA) — the CHI / AXI protocols below the mesh
- [Modern SoC Design](https://github.com/BrendanJamesLynskey/SoC) — same visual style, complementary topics (packaging, CXL, SerDes)

## License

Educational use. Content © Brendan Lynskey. Fonts and Reveal.js retain their own licenses.

# Linux Kernel and Texas Instruments Embedded Linux Contributions — Parth

This repository documents verified public Linux kernel, Linux-MTD, and Texas Instruments embedded Linux work attributed to Parth Mauria Saxena / Parth Saxena under `parth.saxena@ti.com` and related TI public support records.

The purpose of this repository is evidentiary and archival: to collect links, context, and claim boundaries around publicly visible contributions across Linux MTD/NAND, OMAP/TI81xx platforms, NAND bad-block handling, 8-bit / 16-bit NAND bus-width behavior, UBI/UBIFS support, TI EVM bring-up, and U-Boot/MMC clocking support.

## Key Upstream Linux Kernel Contribution

Parth is credited in mainline Linux for the NAND/MTD fix:

**`mtd: return badblockbits back`**

The merged upstream Linux commit credits Parth as:

```text
Reported-by: Saxena, Parth <parth.saxena@ti.com>
Tested-by: Saxena, Parth <parth.saxena@ti.com>
Acked-by: Saxena, Parth <parth.saxena@ti.com>
```

This followed Parth’s original Linux-MTD RFC:

[RFC] mtd: nand: Fix bad block identification issue

The issue involved missing initialization of badblockbits, affecting NAND bad-block identification for drivers using NAND_SKIP_BBTSCAN. Parth demonstrated the practical failure on OMAP hardware, where mounting an empty JFFS2 filesystem on OMAP3EVM failed with an I/O error.

Mainline Linux commit: 

https://github.com/torvalds/linux/commit/26d9be11485ea8c1102c3e8eaa7667412eef4950

## Public Technical Areas

Public records show work and support across:

- Linux MTD / NAND subsystem
- NAND bad-block marker behavior
- OMAP NAND driver behavior
- TI8168 / DM816x / C6A816x / AM389x board bring-up
- TI81xx NAND enablement and performance tuning
- 8-bit / 16-bit NAND bus-width handling
- GPMC / CS0BW board-level configuration
- NAND partition-table and board-file initialization
- UBI / UBIFS compatibility discussions
- JFFS2 / MTD filesystem failure analysis
- U-Boot / MMC / SD boot performance support
- TI81xx MMC clock-frequency configuration
- Customer-facing embedded Linux troubleshooting through TI E2E

## Evidence Index

1. Original Linux-MTD RFC

[RFC] mtd: nand: Fix bad block identification issue

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035221.html

2. Generic NAND-core fix discussion

[PATCH] mtd: return badblockbits back

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035246.html

3. Parth’s Tested-by / Acked-by reply

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035261.html

4. Mainline Linux commit

mtd: return badblockbits back

https://github.com/torvalds/linux/commit/26d9be11485ea8c1102c3e8eaa7667412eef4950

5. TI8168 EVM NAND support thread

[PATCH] ti816x: add support for nand on ti8168 evm

https://lists.infradead.org/pipermail/linux-mtd/2011-September/037922.html

6. TI81xx NAND prefetch-polled performance thread

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/128433/nand-read-speeds-on-linux-2-6-37

7. DM816x 8-bit / 16-bit NAND bus-width thread

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/151629/replace-16-bit-nand-to-8-bit-nand-on-dm816x-evm

8. OMAP NAND subpage / UBI / UBIFS support thread

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/160842/omap-nand-driver-fails-mtd-testsuite-s-sub-page-test

9. NAND bad-block / boot-media troubleshooting thread

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/106504/bad-blocks-on-nand-with-c6a816x-am389x-evm---solved

10. TI81xx U-Boot / MMC clock-frequency support thread

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/144654/how-fast-is-your-sd-read-from-u-boot

## Claim Boundary

Parth identified, reported, tested, and acknowledged a Linux MTD/NAND bad-block regression fix that was merged into mainline Linux, and is credited in the upstream Linux kernel.

Parth also showcased a broader embedded Linux public profile around TI SoC platform enablement, NAND/MTD support, OMAP/TI81xx board bring-up, flash boot media, UBI/UBIFS support, NAND bus-width configuration, and U-Boot/MMC clocking.

This repository does not rewrite authorship of upstream commits. It preserves public attribution and links to the original upstream sources.

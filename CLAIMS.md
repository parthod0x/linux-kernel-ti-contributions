# Claim Wording — Linux Kernel and Texas Instruments Embedded Linux Contributions

This file contains safe, reuse-ready wording for describing Parth’s public Linux kernel and Texas Instruments embedded Linux work.

## Short Version

Credited in mainline Linux for reporting, testing, and acknowledging a Linux MTD/NAND bad-block regression fix merged upstream as `mtd: return badblockbits back`.

## GitHub Profile Version

Public, attributable embedded Linux work from the Texas Instruments period across Linux MTD/NAND, OMAP/TI81xx platform support, NAND bad-block handling, 8-bit / 16-bit NAND bus-width behavior, GPMC/CS0BW behavior, boot-mode diagnostics, UBI/UBIFS support, TI EVM bring-up, and U-Boot/MMC clocking.

Credited in mainline Linux with `Reported-by`, `Tested-by`, and `Acked-by` tags for the NAND/MTD fix `mtd: return badblockbits back`.

## Resume Version

Contributed to embedded Linux and TI SoC platform enablement across Linux MTD/NAND, OMAP/TI81xx board support, NAND bad-block handling, 8-bit / 16-bit NAND bus-width configuration, GPMC/CS0BW behavior, boot-mode diagnostics, UBI/UBIFS support, and U-Boot/MMC clocking. Credited in mainline Linux with `Reported-by`, `Tested-by`, and `Acked-by` tags for identifying and validating the upstream NAND/MTD regression fix `mtd: return badblockbits back`.

## Detailed Professional Version

Parth Mauria Saxena / Parth Saxena contributed to embedded Linux and Texas Instruments SoC platform enablement, with public work across Linux MTD/NAND, OMAP/TI81xx platforms, NAND bad-block detection, 8-bit / 16-bit NAND bus-width handling, UBI/UBIFS support, TI EVM bring-up, and U-Boot/MMC clock-frequency support.

His strongest public upstream Linux contribution is the NAND/MTD fix `mtd: return badblockbits back`, where he is credited in mainline Linux with:

```text
Reported-by: Saxena, Parth <parth.saxena@ti.com>
Tested-by: Saxena, Parth <parth.saxena@ti.com>
Acked-by: Saxena, Parth <parth.saxena@ti.com>
```

This contribution followed his original Linux-MTD RFC, [RFC] mtd: nand: Fix bad block identification issue, which identified missing badblockbits initialization affecting NAND bad-block detection for drivers using NAND_SKIP_BBTSCAN and demonstrated the issue on OMAP hardware through a JFFS2 mount failure on OMAP3EVM.

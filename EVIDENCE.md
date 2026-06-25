# Evidence Index — Linux Kernel and Texas Instruments Embedded Linux Contributions

This file collects public evidence links for Parth’s Linux kernel, Linux-MTD, and Texas Instruments embedded Linux work.

The purpose of this file is to preserve source links, summarize what each source shows, and maintain careful claim boundaries.

## 1. Original Linux-MTD RFC

**Title:** `[RFC] mtd: nand: Fix bad block identification issue`
**Source:** Linux-MTD mailing list
**Date:** April 2011
**Attribution:** Saxena, Parth `<parth.saxena@ti.com>`

Link:

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035221.html

### What this shows

Parth authored an RFC identifying a NAND bad-block identification issue involving missing `badblockbits` initialization.

The issue affected NAND bad-block detection for drivers using `NAND_SKIP_BBTSCAN`.

The RFC demonstrated practical failure on OMAP hardware, specifically an empty JFFS2 filesystem mount failure on OMAP3EVM.

The proposed OMAP-side fix initialized:

```c
info->nand.badblockbits = 8;
```

inside the OMAP NAND driver.

### Claim supported

Parth identified and reported a Linux MTD/NAND bad-block detection regression and proposed a targeted OMAP-side fix.

---

## 2. Generic NAND-Core Fix Discussion

**Title:** `[PATCH] mtd: return badblockbits back`
**Source:** Linux-MTD mailing list
**Author:** Artem Bityutskiy
**Related attribution:** Reported by Parth Saxena

Link:

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035246.html

### What this shows

The maintainer discussion moved the fix from an OMAP-specific driver change into the generic NAND core.

The generic fix restored:

```c
chip->badblockbits = 8;
```

inside `drivers/mtd/nand/nand_base.c`.

The patch credits Parth as the reporter of the issue.

### Claim supported

Parth’s report led to a generic upstream NAND-core fix rather than only a platform-local workaround.

---

## 3. Parth’s Tested-by / Acked-by Reply

**Source:** Linux-MTD mailing list
**Attribution:** Saxena, Parth `<parth.saxena@ti.com>`

Link:

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035261.html

### What this shows

Parth responded to the generic NAND-core fix with:

```text
Tested-By: Saxena, Parth <parth.saxena@ti.com>
Acked By: Saxena, Parth <parth.saxena@ti.com>
```

### Claim supported

Parth tested and acknowledged the generic NAND-core fix that addressed the regression he had reported.

---

## 4. Mainline Linux Commit

**Commit title:** `mtd: return badblockbits back`
**Repository:** `torvalds/linux`
**Commit:** `26d9be11485ea8c1102c3e8eaa7667412eef4950`

Link:

https://github.com/torvalds/linux/commit/26d9be11485ea8c1102c3e8eaa7667412eef4950

Patch link:

https://github.com/torvalds/linux/commit/26d9be11485ea8c1102c3e8eaa7667412eef4950.patch

Additional Linux-MTD review context:

https://lists.infradead.org/pipermail/linux-mtd/2011-April/035258.html

Stable-review mirrors:

https://lkml.iu.edu/1106.0/00080.html  
https://lkml.iu.edu/1106.0/00139.html

### What this shows

The final fix was merged into mainline Linux.

The commit credits Parth Saxena with the following attribution tags:

```text
Reported-by: Saxena, Parth <parth.saxena@ti.com>
Tested-by: Saxena, Parth <parth.saxena@ti.com>
Acked-by: Saxena, Parth <parth.saxena@ti.com>
```

The commit restores:

```c
chip->badblockbits = 8;
```

in the generic NAND core.

### Claim supported

Parth is publicly credited in mainline Linux for reporting, testing, and acknowledging the NAND/MTD regression fix `mtd: return badblockbits back`.

### Claim boundary

The final merged commit was authored by Artem Bityutskiy. The accurate claim is not that Parth authored the final merged commit, but that Parth was credited in mainline Linux as `Reported-by`, `Tested-by`, and `Acked-by`.

---

## 5. TI8168 EVM NAND Support Thread

**Title:** `[PATCH] ti816x: add support for nand on ti8168 evm`
**Source:** Linux-MTD mailing list
**Date:** September 2011

Link:

https://lists.infradead.org/pipermail/linux-mtd/2011-September/037922.html

### What this shows

This Linux-MTD thread concerns adding NAND support for the TI8168 EVM.

The patch adds NAND partition-table and NAND initialization support in the TI8168 EVM board file.

### Claim supported

Parth’s public Linux-MTD footprint includes TI8168 EVM NAND enablement and board-level NAND integration work.

---

## 6. TI81xx NAND Prefetch-Polled Performance Thread

**Topic:** NAND read performance on Linux 2.6.37
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/128433/nand-read-speeds-on-linux-2-6-37

### What this shows

Parth participated in a TI E2E NAND performance discussion for TI81xx hardware.

The thread includes a patch changing NAND transfer type from:

```c
NAND_OMAP_POLLED
```

to:

```c
NAND_OMAP_PREFETCH_POLLED
```

### Claim supported

Parth publicly supported NAND performance tuning on TI81xx platforms, including prefetch-polled NAND transfer behavior.

---

## 7. DM816x 8-bit / 16-bit NAND Bus-Width Thread

**Topic:** Replacing 16-bit NAND with 8-bit NAND on DM816x EVM
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/151629/replace-16-bit-nand-to-8-bit-nand-on-dm816x-evm

### What this shows

Parth participated in a TI E2E discussion about replacing the default 16-bit NAND device with an 8-bit NAND device on DM816x EVM.

The thread discusses CS0BW, 8-bit / 16-bit NAND bus-width selection, GPMC behavior, and board-level runtime configuration.

The thread also records that TI had earlier used the CS0BW switch in an inverted/backward-compatible manner for 8-bit / 16-bit NAND detection, then planned to rectify the code so CS0BW OFF corresponded to 8-bit NAND and CS0BW ON corresponded to 16-bit NAND.

Parth also pointed to an Arago `linux-omap3` reference for the CS0BW behavior change:

http://arago-project.org/git/projects/?p=linux-omap3.git;a=commit;h=3064bce8324f67a6ac64b97ddf89e92b8aaf22b3

### Claim supported

Parth’s public TI support footprint includes NAND bus-width configuration and board-level flash interface bring-up for DM816x platforms.

---

## 8. OMAP NAND Subpage / UBI / UBIFS Support Thread

**Topic:** OMAP NAND driver failing MTD testsuite subpage test
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/160842/omap-nand-driver-fails-mtd-testsuite-s-sub-page-test

### What this shows

Parth participated in support discussion around OMAP NAND subpage behavior, MTD tests, UBI, and UBIFS compatibility.

The thread discusses driver limitations, documented workarounds, and future support planning.

### Claim supported

Parth’s public Texas Instruments embedded Linux support includes NAND subpage behavior, MTD test compatibility, UBI, and UBIFS guidance.

---

## 9. NAND Bad-Block / Boot-Media Troubleshooting Thread

**Topic:** Bad blocks on NAND with C6A816x / AM389x EVM
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/106504/bad-blocks-on-nand-with-c6a816x-am389x-evm---solved

### What this shows

The thread involves NAND bad-block behavior and boot-media troubleshooting on C6A816x / AM389x EVM platforms.

It also references NAND, NOR, and SPI boot contexts.

### Claim supported

Parth’s public support footprint includes NAND bad-block troubleshooting and TI EVM boot-media debugging.

### Claim boundary

This thread is support evidence, not a standalone upstream patch attribution.

---

## 10. TI81xx U-Boot / MMC Clock-Frequency Support Thread

**Topic:** SD read speed from U-Boot
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/144654/how-fast-is-your-sd-read-from-u-boot

### What this shows

Parth participated in TI E2E support around U-Boot MMC / SD read performance and clock-frequency configuration on TI81xx platforms.

The thread points to clock-frequency handling relevant to TI816x and TI814x.

### Claim supported

Parth’s public TI support footprint includes U-Boot, MMC / SD boot performance, and clock-frequency configuration guidance.

---

## 11. DM8168 EVM Boot-Option / GPMC Bus-Width Thread

**Topic:** DM8168 EVM boot option
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/139834/dm8168-evm-boot-option

### What this shows

Parth participated in a TI E2E discussion about DM8168 EVM boot-option switch configuration, GPMC bus-width behavior, and NAND boot-mode interpretation.

The user asked why the documented NAND boot-mode switch setting appeared to indicate 8-bit NAND even though the board NAND was 16-bit.

Parth explained that earlier U-Boot and kernel support assumed 16-bit NAND, so the GPMC bus-width switch was not used to configure anything. In a later release, TI added 8-bit NAND support and used the GPMC bus-width switch to support both 8-bit and 16-bit NAND, while maintaining backward compatibility with previous releases.

### Claim supported

Parth’s public TI support footprint includes DM8168 EVM boot-option interpretation, GPMC bus-width behavior, and 8-bit / 16-bit NAND release-compatibility guidance.

### Claim boundary

This is support evidence and release-behavior explanation, not a standalone upstream Linux patch attribution.

---

## 12. DM816x / AM389x Board-Hang / Boot-Mode Diagnostics Thread

**Topic:** TI DM816x / AM389x EVM board hangs while booting
**Source:** TI E2E forum

Link:

https://e2e.ti.com/support/processors-group/processors/f/processors-forum/161332/ti-dm816x-am389x-evm-board-hangs-while-booting

### What this shows

Parth participated in TI E2E board-bring-up troubleshooting for a DM816x / AM389x EVM boot hang around `omap2-nand driver initializing`.

The boot logs in the thread also show SPI flash detection through `m25p80 spi1.0` and MTD partition creation for SPI flash before NAND initialization.

Parth advised that the issue did not look like a NAND-driver software issue and suggested checking:

* whether the NAND switch was turned on
* whether the NAND bus-width switch was set appropriately for the 8-bit / 16-bit NAND used
* whether boot-mode pins were set appropriately

### Claim supported

Parth’s public TI support footprint includes board-level boot diagnostics across NAND, SPI flash boot logs, NAND bus-width switching, and boot-mode pin configuration on DM816x / AM389x EVM platforms.

### Claim boundary

This is support and diagnostic evidence, not a standalone upstream Linux patch attribution.

---

## Consolidated Evidence-Based Claim

The strongest verified claim is:

> Parth Saxena is credited in mainline Linux as `Reported-by`, `Tested-by`, and `Acked-by` for the NAND/MTD regression fix `mtd: return badblockbits back`.

The broader public evidence supports work and support across:

* Linux MTD / NAND
* NAND bad-block detection
* OMAP NAND driver behavior
* TI8168 / DM816x / C6A816x / AM389x board bring-up
* TI81xx NAND performance tuning
* 8-bit / 16-bit NAND bus-width handling
* GPMC / CS0BW board-level configuration
* NAND partition-table and board-file initialization
* UBI / UBIFS support discussions
* JFFS2 / MTD filesystem failure analysis
* U-Boot / MMC / SD boot support
* TI81xx clock-frequency configuration
* TI E2E customer-facing embedded Linux troubleshooting
* DM8168 boot-option and GPMC bus-width behavior
* DM816x / AM389x boot-mode and switch-level diagnostics

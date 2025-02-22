xemu is a low-level, full-system emulator which emulates the actual hardware of
the Xbox; this means that in order to actually run xemu, you must have a copy
of the stuff that a real Xbox needs when it turns on:

1. [MCPX Boot ROM Image](#mcpx-boot-rom-image)
2. [Flash ROM Image (BIOS)](#flash-rom-image-bios)
3. [Hard Disk Image](#hard-disk-image)

Unfortunately, distributing some of these items would violate copyright laws, so
you'll need to acquire them on your own.

!!! warning "Disclaimer"
    The xemu project does not endorse or promote piracy. We don't link to
    copyrighted files, or discuss how to acquire them. The only legal way to
    acquire these files is to dump them from *your real, physical Xbox*. Please
    don't ask us how to get them.

## MCPX Boot ROM Image

    MD5 (mcpx_1.0.bin) = d49c52a4102f6df7bcf8d0617ac475ed

If your MCPX dump has an MD5 of `196a5f59a13382c185636e691d6c323d`, you dumped
it badly and it's a couple of bytes off. It should start with `0x33 0xC0` and end
with `0x02 0xEE`.

There is also a open-source alternative to a real MCPX dump, known as [Fancy Mouse Boot ROM](https://github.com/SnowyMouse/fancy-mouse-boot-rom).
It has high compatibility and is nearly functionally equivalent. 
Releases can be found [here](https://github.com/SnowyMouse/fancy-mouse-boot-rom/releases).
!!! warning "Revisions"
    The Fancy Mouse Boot ROM .zip contains two files "mouse_rev0.bin" and "mouse_rev1.bin".
    Choose "mouse_rev0.bin" as that is the equivalent to a MCPX 1.0 image, not a MCPX 1.1 in which we don't support currently.
## Flash ROM Image (BIOS)

Xbox compatible BIOS. Just like a real Xbox, running an unmodified retail BIOS will
not allow booting unofficial software.

People have reported most success using the modified retail "COMPLEX 4627" BIOS.

## Hard Disk Image

You can use a pre-built 8G Xbox HDD image, free of any copyrighted content, and
only containing a dummy dashboard.

[Download Pre-formatted Xbox Hard Disk Image ](https://github.com/mborgerson/xemu-hdd-image/releases/latest/download/xbox_hdd.qcow2.zip){ .md-button .md-button--secondary }

!!! note
    By design, this particular drive image does not contain the official Xbox
    dashboard, but instead contains only an **unsigned** dummy dashboard. [More
    information](dashboard.md)

??? "Alternative Options"
    **Alternative 1:** Image your real Xbox HDD

    This is the most authentic way to do it. Unlock your drive, connect it to a
    computer, and `dd` the entire contents of the drive straight to a file. This
    file can be used as-is with xemu.

    **Alternative 2:** Build a new HDD image from scratch

    You can also create an Xbox hard-disk image using XboxHDM. Directions on how
    to do this [can be found here](https://github.com/mborgerson/xemu-hdd-image).

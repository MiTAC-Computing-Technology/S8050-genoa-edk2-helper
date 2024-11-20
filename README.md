# S8050-genoa-edk2-helper

This is source code setup repository for MiTAC S8050 of Genoa/OpenSIL/EDK2.


## Clone Repositories

1. Execute init.sh to clone source codes and apply patches
2. The repositories and folder structure will be:
  - AGCL-R (Branch: genoa_poc)
  - amd_firmwares (Branch: genoa_poc)
  - AmdOpenSilPkg
    - opensil-uefi-interface (Branch: genoa_poc)
      - OpenSIL (Branch: genoa_poc)
  - edk2 (Branch: edk2-stable202205)
  - edk2-platforms (Tag: b8ffb76b471dae5e24badcd9e04033e8c9439ce3)
  - Patches
  - Platform (Branch: genoa_poc)


## Build and Deploy

1. Execute ./dbuild.sh s8050 --edk2args="-b DEBUG" to build debug rom
2. Deploy R8000000000N.FD to 32MB SPI flash of S8050


## Progress

- With these repositories, S8050 + Genoa can boot to EDK2 Shell successfully
- Support USB and SATA devices
- Debug messages are available through BMC SOL
- When using MiTAC legacy BMC, please set PcdSetBmcVgaToHost to TRUE to switch VGA control from BMC to Host
- Only verify in Linux build environment


## Reference

- All openSIL related repositories are forked from https://github.com/openSIL; the projected plan is also aligned with AMD's roadmap of openSIL
- Aspeed Driver version is 1.13.05 from Aspeed website (BmcGopDxe)

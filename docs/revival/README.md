# Fork revival review

Reviewed 18 October 2026. This repository is a fork of [VitruvianOS/Vitruvian](https://github.com/VitruvianOS/Vitruvian); preserve upstream authorship and licences. Source presence does not establish Henric-authored implementation or a successful fork build.

| Path | Role |
| --- | --- |
| src/, headers/ | OS, desktop and API source |
| build/, configure, CMakeLists.txt | Build profiles, packaging and image construction |
| data/ | System resources |
| .gitmodules | External dependencies, including Nexus |
| docs/revival/ | Fork-specific review and next milestones |

## Verified by inspection

The base profile selects desktop components, Terminal and system services. mkiso.sh contains actual filesystem, kernel and bootloader assembly. The configure script supports x86_64; arm64 is explicitly a stub. The README describes an experimental OS. No Actions runs or releases were returned for this fork at review time. No compile, ISO build, VM boot or hardware test was executed in this review.

## Revival sequence

1. Record the fork and upstream commits and compare local changes before synchronising.
2. Resolve pinned submodules and documented build prerequisites in a disposable build VM.
3. Produce a reproducible x86_64 build and retain logs and checksums.
4. Boot the image in a VM; test desktop, Terminal, input, storage and shutdown.
5. Qualify installation, updates and hardware separately before a release candidate.

The image script uses mounts, chroot and package installation. Use an isolated build VM. Debug configuration includes password-based root SSH; review image defaults before distributing artifacts. Existing build paths and submodule locations were preserved by this documentation cleanup.

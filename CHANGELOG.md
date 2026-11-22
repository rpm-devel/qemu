# qemu Changelog

## 11.0.2-2

- Build on EL8, EL9 and EL10 and replace the distro `qemu-kvm` packages
  (Epoch 19 outranks EL8 15, EL9 17, EL10 18; the RHEL `qemu-kvm-*`
  subpackage names are provided and obsoleted)
- EL8 builds QEMU 9.0.4 because QEMU >= 9.1 needs glib2 >= 2.66 (EL8 has 2.56);
  EL9 and EL10 build 11.0.2
- QEMU builds with its bundled meson, so `meson` is no longer a build dependency
- Drop configure options removed upstream and the cris, nios2 and microblazeel
  system targets on releases that no longer ship them
- Guard libiscsi, SDL2, glusterfs, virglrenderer, libbpf, dbus display and
  firmware packages for the releases that do not ship them
- Add `qemu-audio-dbus`, `qemu-ui-dbus` and `qemu-device-uefi-vars` subpackages
- Remove `qemu-virtiofsd` (the C implementation was removed upstream)
- Provide `/usr/libexec/qemu-kvm` and `/usr/bin/qemu-kvm` on aarch64
- Static system emulators are skipped on RHEL (no `pixman-static`)
- `--without user_static` and `--without system_static` skip the static passes

## 11.0.2

- Add `mock/` directory with per-distro mock configs for EL8, EL9, EL10
  (x86\_64 and aarch64) referencing the org-level casjay templates

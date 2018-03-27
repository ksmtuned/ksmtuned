# ksmtuned

This repo provides the following

- ksmtuned: a simple script that controls whether (and with what vigor)
  linux [KSM](https://www.linux-kvm.org/page/KSM) (Kernel Samepage Merging)
  should search for duplicated pages of qemu processes, and a systemd
  .service file to enable/disable it.
- ksmctl and ksm.service: A systemd service to start/stop KSM entirely

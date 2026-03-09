# playbooks

Ansible playbooks for Arch Linux local environment setup.

## Usage

```bash
ansible-playbook -i inventory/localhost site.yml
```

## Roles

### packages

Installs the following packages via `pacman`:

- **Base development tools**: `linux-headers`, `base-devel`, `git`, `bash-completion`
- **Camera and multimedia**: `pipewire-libcamera`, `libcamera-tools`, `pipewire-v4l2`, `v4l2loopback`
- **Network**: `networkmanager-openvpn`
- **Desktop integration**: `xdg-desktop-portal-gnome`
- **System utilities**: `less`, `chezmoi`, `sbctl`
- **Docker**: `docker`, `docker-compose`, `docker-buildx`

Also enables and starts the Docker service.

### secure_boot

Sets up Secure Boot using `sbctl`:

1. Creates secure boot keys (if not already installed)
2. Signs EFI binaries:
   - `/boot/EFI/BOOT/BOOTX64.EFI`
   - `/boot/vmlinuz-linux`
   - `/boot/EFI/systemd/systemd-bootx64.efi`
   - `/boot/EFI/Linux/arch-linux.efi`
3. Verifies signed binaries
4. Removes immutable attributes from EFI variables
5. Enrolls secure boot keys (Microsoft keys included via `-m` flag)
# 02 Boot or Change System into Different Operating Modes

### Understanding Systemd and Targets

Systemd is an init system and system manager that has become the standard for many Linux distributions. It is used to bootstrap the user space and manage system processes after booting. Systemd introduces the concept of 'targets' which serve a similar purpose as runlevels but are more flexible.

Each target is named instead of numbered and is intended to serve a specific purpose. For example, `multi-user.target` is for a multi-user text mode, and `graphical.target` is for a full graphical user interface with networking.

### Checking Current Target

To check the current target, you use the `systemctl` command:

```bash
systemctl get-default
```

This command will return the default target, which is equivalent to the default runlevel.

### Changing Targets

To change the current target, use the `systemctl` command followed by the `isolate` option:

```bash
sudo systemctl isolate graphical.target
```

This command will switch the system to a graphical user interface mode.

### Setting Default Target

To set a default target, use the `set-default` command:

```bash
sudo systemctl set-default multi-user.target
```

This command sets the system to boot into multi-user text mode by default.

### Emergency and Rescue Modes

There are times when the system may encounter issues that prevent it from booting properly. For such cases, systemd provides 'emergency' and 'rescue' modes.

**Rescue Mode (`rescue.target`):** A single user mode that is used for recovery purposes.

To enter rescue mode from the boot menu, you can add `systemd.unit=rescue.target` to the kernel command line. Alternatively, from a running system:

```bash
sudo systemctl isolate rescue.target
```

The system will prompt for the root password.

**Emergency Mode (`emergency.target`):** Similar to rescue mode but with even fewer services started.

To boot into emergency mode, add `systemd.unit=emergency.target` to the kernel command line or from a running system:

```bash
sudo systemctl isolate emergency.target
```

### Rebooting the System

To reboot the system, use the `reboot` command:

```bash
sudo systemctl reboot
```

Or simply:

```bash
sudo reboot
```

### Powering Off the System

To power off the system, use the `poweroff` command:

```bash
sudo systemctl poweroff
```

Or simply:

```bash
sudo poweroff
```

### Example Output

Here's an example of changing the default target and then rebooting the system:

```bash
$ sudo systemctl set-default multi-user.target
$ sudo systemctl get-default
multi-user.target
$ sudo reboot
```

After running these commands, the system will reboot into multi-user mode.

### Using `isolate` Command

The `isolate` command is used to change to a different target without changing the default target:

```bash
sudo systemctl isolate multi-user.target
```

This command will switch the system to multi-user mode for the current session.

Remember that changing system states and targets can affect all users on a system. Always ensure that you are not disrupting critical services or other users' work.

By understanding and practicing these commands, you can effectively manage the state of a Linux system, which is a key component of the LFCS exam curriculum.
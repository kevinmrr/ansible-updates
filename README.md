# ansible-updates

An Ansible playbook that automates system package updates across Linux hosts, with automatic reboots when required.

## Supported Platforms

| Distro | Package Manager |
|---|---|
| Ubuntu / Debian | `apt` |
| RHEL / CentOS 7 / Amazon Linux | `yum` |
| RHEL 8+ / Fedora | `dnf` |

## Prerequisites

- Ansible 2.9+
- SSH key-based access to target hosts
- A user with `sudo` / `become` privileges on remote hosts

## Setup

1. Clone the repo
   ```bash
   git clone https://github.com/<your-username>/ansible-updates.git
   cd ansible-updates
   ```

2. Edit `inventory/hosts` and replace the placeholder hosts with your own.

3. Update `ansible.cfg` if your SSH key path differs from the default.

## Usage

Run updates on all hosts:
```bash
ansible-playbook -i inventory/hosts update.yml
```

Target only Debian/Ubuntu hosts:
```bash
ansible-playbook -i inventory/hosts update.yml --tags debian
```

Target only RHEL/CentOS/Fedora hosts:
```bash
ansible-playbook -i inventory/hosts update.yml --tags rhel
```

## Project Structure

```
ansible-updates/
├── ansible.cfg          # Ansible configuration
├── update.yml           # Main playbook
└── inventory/
    └── hosts            # Inventory template
```

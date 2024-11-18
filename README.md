# NetObserv Flow Collector Ansible Role

This ansible role installs and configures the NetObserv Flow Collector on Debian-based (Debian, Ubuntu) and RHEL-based (RHEL, AlmaLinux) Linux distributions. The role handles package installation, dependency management, GPG verification, configuration deployment, and service management.

## Requirements

- Ansible 2.9 or higher
- Target systems running:
  - **Debian-based**: Debian 11 (Bullseye), Debian 12 (Bookworm), Ubuntu 20.04 LTS, 22.04 LTS, or 24.04 LTS
  - **RHEL-based**: RHEL 8.x, RHEL 9.x, RockyLinux 8.x, RockyLinux 9.x, AlmaLinux 8.x, or AlmaLinux 9.x

### Role Variables

| Variable                 | Default Value                                              | Description                                         |
|:-------------------------|:-----------------------------------------------------------|:----------------------------------------------------|
| `netobserv_version`      | `"7.5.1"`                                                  | The default version of the NetObserv Flow Collector |
| `netobserv_package_deb`  | `"flow-collector_{{ netobserv_version }}_linux_amd64.deb"` | The Debian package filename for NetObserv           |
| `netobserv_package_rpm`  | `"flow-collector-{{ netobserv_version }}-1.x86_64.rpm"`    | The RPM package filename for NetObserv              |

## Example Playbook

Here’s how to use the `elastiflow.netobserv` role in your playbook:

```yaml
# playbook.yml
---
- name: Deploy NetObserv Flow Collector
  hosts: all
  become: true
  roles:
    - elastiflow.netobserv

  vars:
    netobserv_version: "7.5.1"  # Optional: Override default version
```

## Usage Instructions

1. **Clone or Copy the Role**: Place the `elastiflow.netobserv` role directory in your Ansible roles directory or include it in your project structure.

2. **Include the Role in Your Playbook**: Reference the `elastiflow.netobserv` role in your playbook as shown in the example above.

3. **Run the Playbook**:
   - **Check Mode (Dry Run)**:

     ```bash
     ansible-playbook playbook.yml --check
     ```

   - **Apply Changes**:

     ```bash
     ansible-playbook playbook.yml
     ```

## License

This project is licensed under the [Apache 2.0 License](./LICENSE).

# OPNsense Ansible Management

This repository contains an Ansible setup to manage an OPNsense firewall using the `oxlorg.opnsense` collection.

## Prerequisites

1.  **Ansible**: Ensure Ansible is installed on your machine.
2.  **Python**: Python 3 is required.

## Setup

1.  **Install Dependencies**:
    Install the required Ansible collection:
    ```bash
    ansible-galaxy collection install -r requirements.yml
    ```

2.  **Configure Inventory**:
    Edit `inventory/hosts.yml` and update the `ansible_host` with your OPNsense firewall's IP address or hostname.

3.  **Configure Credentials**:
    Edit `playbook.yml` and update the `opnsense_api_key` and `opnsense_api_secret` variables.
    *Note: For production, it is highly recommended to use Ansible Vault to encrypt these secrets.*

    To generate API keys in OPNsense:
    - Go to **System > Access > Users**.
    - Edit the user (e.g., `root` or a dedicated automation user).
    - Scroll down to **API keys** and click the **+** button to generate a new key/secret pair.

## Usage

Run the playbook:

```bash
ansible-playbook playbook.yml
```

## Example

The `playbook.yml` currently contains a task to create a firewall alias named `ANSIBLE_TEST_ALIAS`.

## Documentation

For more information on the available modules and usage, refer to the [Ansible OPNsense Collection Documentation](https://ansible-opnsense.oxl.app/usage/2_basic.html).

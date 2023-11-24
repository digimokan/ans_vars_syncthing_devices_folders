# ans_vars_syncthing_devices_folders

Define a set of LAN-common syncthing devices and shared syncthing folders.

[![Release](https://img.shields.io/github/release/digimokan/ans_vars_syncthing_devices_folders.svg?label=release)](https://github.com/digimokan/ans_vars_syncthing_devices_folders/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Usage](#usage)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Vars](#role-vars)
* [Contributing](#contributing)

## Purpose

* Define a set of devices on the LAN that will participate in sharing via
  syncthing.
* Define a set of common folders that may be shared among devices. Devices
  may choose to share/sync any or all of these folders.

## Usage

* Intended to be used by an ansible role that configures syncthing for a
  machine, such as
  [ans_role_config_syncthing](https://github.com/digimokan/ans_role_config_syncthing).

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_vars_syncthing_devices_folders
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role with `import_role`, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Define a set of LAN-common syncthing devices and shared syncthing folders"
         ansible.builtin.import_role:
           name: ans_vars_syncthing_devices_folders
           public: true
   ```

## Role Vars

See the role `vars` files:

  * [vars](../vars/main/)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_vars_syncthing_devices_folders/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).


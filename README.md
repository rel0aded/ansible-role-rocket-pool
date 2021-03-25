ansible-role-rocket-pool
=========

Ansible role to deploy the Rocket Pool software stack for Ethereum 2.0 staking.

Created as a way to build a repeatable installation of Rocket Pool, exposing various options for Geth (ETH1 client) and the four ETH2 clients (Lighthouse, Nimbus, Prysm, Teku) to surface their functionality and allow configuration that survives a Rocket Pool upgrade.

Additionally, integrates the work of [jclapis' Rocket Pool Raspberry Pi Guide](https://github.com/jclapis/rp-pi-guide) for various optimisations, as well as [YorickDowne's Prometheus/Grafana Docker stack](https://github.com/yorickdowne/grafana-for-rpool) for monitoring.

If the `monitoring` variable is set to true, Prometheus access will be available at http://\<HOST-IP\>:3000 with the credentials `admin:admin` after completion (these should be changed to something secure on first login). Pre-configured dashboards are available; however, Nimbus and Teku are currently not supported as data sources.

Requirements
------------

- x86_64 Linux host (for now, will likely be expanded to all platforms supported by the [rocketpool](https://github.com/rocket-pool/smartnode-install/releases) binary in due course).

Role Variables
--------------

Feature Set Variable

| Name  | Default Setting | Description |
| --- | --- | --- |
| start_containers | false | Determines whether to start all deployed Docker containers as part of the execution, or start manually afterwards.<br />Disabled by default while still in development  |
| monitoring | true  | Deploys [YorickDowne's Prometheus/Grafana Docker stack](https://github.com/yorickdowne/grafana-for-rpool) as part of the installation. Also configures the necessary client flags to enable monitoring |

Rocket Pool Variables

| Name  | Default Setting | Description |
| --- | --- | --- |
| rocket_pool_version | latest | Which release version to install.<br />Examples include "latest" or "tag/1.0.0-beta.0"  |
| installation_mode | docker | Install the Rocket Pool stack as Docker containers or native services.<br />Docker only for now |

Dependencies
------------

- [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker/)

Usage
----------------

```
ansible-galaxy install -r requirements.yml
```

```
- hosts: servers
  roles:
    - { role: username.rolename, x: 42 }
```

License
-------

[BSD 3-Clause](LICENSE)

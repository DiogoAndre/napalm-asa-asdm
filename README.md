[![Build Status](https://travis-ci.org/napalm-automation-community/napalm-asa-asdm.svg?branch=master)](https://travis-ci.org/napalm-automation-community/napalm-asa-asdm)
[![PyPI](https://img.shields.io/pypi/v/napalm-asa-asdm.svg)](https://pypi.python.org/pypi/napalm-asa)

# napalm-asa-asdm

This is a [NAPALM](https://github.com/napalm-automation/napalm) community driver for the Cisco ASA platform, utilizing the ASDM HTTPS interace to communicate with the device.

If your goal is using the ASA REST API to communicate with the device, please refer to [napalm-asa](https://github.com/napalm-automation-community/napalm-asa)

## Minimum Requirements

This driver makes use of the ASDM HTTPS Interface. Before using this driver make sure you have can access your device using ASDM.

## Quick start

```shell
pip install napalm-asa-asdm
```

```python
from napalm import get_network_driver

driver = get_network_driver("asa")
device = driver(hostname='192.168.1.1', username='cisco', password="cisco", optional_args = {'port': 8443})
device.open()
facts = device.get_facts()
device.close()
```

Check the full [NAPALM Docs](https://napalm.readthedocs.io/en/latest/index.html) for more detailed instructions.

## Supported Getters

| Getter                    | Support  |
|---------------------------|----------|
| get_arp_table             |  ❌      |
| get_bgp_config            |  ❌      |
| get_bgp_neighbors         |  ❌      |
| get_bgp_neighbors_detail  |  ❌      |
| get_config                |  ❌      |
| get_environment           |  ❌      |
| get_facts                 |  ❌      |
| get_firewall_policies     |  ❌      |
| get_interfaces            |  ❌      |
| get_interfaces_counters   |  ❌      |
| get_interfaces_ip         |  ✅      |
| get_ipv6_neighbors_table  |  ❌      |
| get_lldp_neighbors        |  ❌      |
| get_lldp_neighbors_detail |  ❌      |
| get_mac_address_table     |  ❌      |
| get_network_instances     |  ❌      |
| get_ntp_peers             |  ❌      |
| get_ntp_servers           |  ❌      |
| get_ntp_stats             |  ❌      |
| get_optics                |  ❌      |
| get_probes_config         |  ❌      |
| get_probes_results        |  ❌      |
| get_route_to              |  ❌      |
| get_snmp_information      |  ❌      |
| get_users                 |  ❌      |
| is_alive                  |  ✅      |
| ping                      |  ❌      |
| traceroute                |  ❌      |

## Setting up a Lab Environment

Mock tests are usefull for quickly iterating when writing a new getter of fixing a bug, but you do want to test on a 'real' device to make sure everything works as expected. One of the most convenient ways is to use an ASAv running on Virtualbox + Vagrant. @bobthebutcher has a nice write up on [how to setup an ASAv with Vagrant.](https://codingpackets.com/blog/cisco-asa-vagrant-box-install/)

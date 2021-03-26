[![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![Python 3.7](https://img.shields.io/badge/python-3.7-blue.svg)](https://www.python.org/downloads/release/python-370/)
[![Python 3.8](https://img.shields.io/badge/python-3.8-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Python 3.9](https://img.shields.io/badge/python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)

# Nornir3_CDP_map
Set descriptions on interfaces according to the hostname collected from connected CDP-Neighbor.

Author: nouse4it <github@schlueter-online.net>

## nornir_cdp_map.py
Illustrate the following conecepts:
- Set descriptions on interfaces according to the hostname collected from connected CDP-Neighbor
- This script also collects the description of the corresponding pyhsical member interfaces of port-channel and renames the PO accordingly

## Use Case Description

The script is intended to automatically put the correct desription on every port.
The script collects all cdp neighbor information from all ports.
It then configures the collected hostname informaiton on the corresponding interface (incl. Port-channel)
The script is able to perform the update on multiple devices in parallel. This makes it possible to run the script on many devices at once.

## Installation
Pleae use at least NORNIR Version 3.0
Following Packtes, Modules and Requirements are needed:
    
    genie==21.2.3
    nornir==3.1.0
    nornir-jinja2==0.1.2
    nornir-napalm==0.1.2
    nornir-netmiko==0.1.1
    nornir-utils==0.1.2
    paramiko==2.7.2
    pyats==21.2
    
For more informations see ---> https://github.com/nornir-automation/nornir
Python Version must be at least v3.6.8
## Usage
Please create the neccessary inventory files that nornir works with, and adjust them to your enviroment.
For that please use the following files:

* nornir3_config.yaml     ---> basis config of how nornir should handle connections and where to gather informations
* nornir3_defaults.yaml   ---> can be left empty, but must be present as a file
* nornir3_groups.yaml     ---> is used to group your hosts an provide a plattform info (used for authentication)
* nornir3_hosts.yaml      ---> is used to put in the hosts you want to run the scripts against in yaml format
    
For more help how to setup a inventory please see ---> https://nornir.readthedocs.io/en/latest/tutorial/inventory.html

When you finisched setting up the inventory you can run the script with python3 nornir3_cdp_map.py
The scripts start an will ask you for the follwing input:
    
* Username for login on the switches
* Password for login on the switches

## Licensing info

Please see [LICENSE](https://github.com/nouse4it/netmiko_IOS_Update/blob/master/LICENSE)

## Credit
The original idea and basic setup of this script came from @IPvZero 
Please check out his repo here on github. 
I added the possibility to rename port channels and enable CDP on specific ports in a VLAN.

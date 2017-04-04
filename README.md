# ansible_cisco_ios_03

ansible playbook that automate network device configuration, provisioning and maintaining a Cisco device running IOS

topology: https://1drv.ms/i/s!Anv8ThLcbJaXg9ck6R1z2N3iPsyX5w

module use in play:
 - ios_config (jinja2 template and filters)
 - ios_command
 - ntc-ansibe (ntc_show_command) https://github.com/networktocode/ntc-ansible

configuration:
 - vlan
 - access port/s, port-channel
 - trunk ports, port-channel
 - interfaces
    - svi
    - routed ports
    - layer 3 interface
  - routing protocols
    - eigrp (named)
  - gateway load balancing protocol(GLBP)

the deploy-main.yml use to deploy new installed network devices added to the topology.

the snip-*.yml use to provision config snippets to devices without runnning the whole playbook.
  example, if you just wanted to configure addtional access or trunk ports.

the order of command/operation are base on what you configure on the actual device.
  example, when you create/add access ports using snip-access-ports.yml, first it will create run a vlan role

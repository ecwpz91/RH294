
# Two host groups always exist:

* The `all` host group contains every host explicitly listed in the inventory.
* The `ungrouped` host group contains every host explicitly listed in the inventory that is not a member of any other group.

# Verifying the Inventory

When in doubt, use the ansible command to verify a machine's presence in the inventory:

```sh
[user@controlnode ~]$ ansible washington1.example.com --list-hosts
```

# Exercise

Create a custom static inventory file. Information about your four managed hosts is listed in the following table. You will assign
each host to multiple groups for management purposes based on the purpose of the host,the city where it is located, and the deployment environment to which it belongs.
In addition, groups for US cities (Raleigh and Mountain View) must be set up as children of the group us so that hosts in the United States can be managed as a group.

| Host Name   | Purpose  | Location  | Environment  |
|---|---|---|---|
| servera.lab.example.com  | Web server  | Raleigh  | Development  |
| serverb.lab.example.com  | Web server  | Raleigh  | Testing  |
| serverc.lab.example.com  | Web server  | Mountain View  | Production  |
| serverd.lab.example.com  | Web server  | London  | Production  |

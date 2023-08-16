# Nutanix Role to set the initial admin password for Prism

This Ansible to set the initial admin password for either a Nutanix cluster or Prism Central.


## Role Variables

| Variable                                          | Required | Default | Choices                   | Comments                                                                                               |
|---------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------------------------|
| nutanix_prism_pwd_host                            | yes      |         |                           | The IP address or FQDN for the Prism (Element or Central).                                             |
| nutanix_prism_pwd_username                        | no       | "admin" |                           | A valid username with appropriate rights to access the Nutanix API. .                                  |
| nutanix_prism_pwd_port                            | no       | 9440    |                           | The Prism TCP port                                                                                     |
| validate_certs                                    | no       | no      | yes / no                  | Whether to check if Prism UI certificates are valid.                                                   |
| nutanix_debug                                     | no       | False   | True / False              | Whether to output variable contents for debugging purposes.                                            |
| nutanix_prism_initial_password                    | yes      |         |                           | The default password for the 'admin' user account.                                                     |
| nutanix_prism_new_password                        | yes      |         |                           | The new password for the 'admin' user account.                                                         |


## Dependencies

None


## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
  - role: grdavies.role_nutanix_prism_initial_password
  vars:
    nutanix_prism_host: 10.38.185.37
    nutanix_prism_username: admin
    nutanix_prism_initial_password: nutanix/4u
    nutanix_prism_new_password: nx2Tech165!
```


## License

See LICENSE.md

## Author Information

Ross Davies

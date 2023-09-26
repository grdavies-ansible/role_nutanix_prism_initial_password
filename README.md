# Nutanix Role to set the initial admin password for Prism

This Ansible to set the initial admin password for either a Nutanix cluster or Prism Central.

## Input Variables

| Variable                                             | Required | Default | Choices                   | Comments                                                                                               |
|------------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_initial_password_host             | yes      |         |                           | The IP address or FQDN for the Prism (Element or Central).                                             |
| role_nutanix_prism_initial_password_username         | no       | "admin" |                           | A valid username with appropriate rights to access the Nutanix API. .                                  |
| role_nutanix_prism_initial_password_port             | no       | 9440    |                           | The Prism TCP port                                                                                     |
| role_nutanix_prism_initial_password_validate_certs   | no       | false   | true / false              | Whether to check if Prism UI certificates are valid.                                                   |
| role_nutanix_prism_initial_password_debug            | no       | false   | true / false              | Whether to output variable contents for debugging purposes.                                            |
| role_nutanix_prism_initial_password_default_password | yes      |         |                           | The default password for the 'admin' user account.                                                     |
| role_nutanix_prism_initial_password_new_password     | yes      |         |                           | The new password for the 'admin' user account.                                                         |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
  - role: grdavies.role_nutanix_prism_initial_password
  vars:
    nutanix_prism_host: 10.38.185.37
    nutanix_prism_username: admin
    role_nutanix_prism_initial_password_default_password: nutanix/4u
    role_nutanix_prism_initial_password_new_password: nx2Tech165!
```


## License

See LICENSE.md

## Author Information

Ross Davies

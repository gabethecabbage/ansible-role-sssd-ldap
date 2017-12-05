# ansible-role-sssd-ldap

Installs, configures and enables sssd/ldap authentication for RHEL/Ubuntu 

## Requirements

None

## Role Variables
| Variable Name             | Defaults | Description                                                        |
|---------------------------|----------|--------------------------------------------------------------------|
| ldap_schema               |rfc2307bis|                                                                    |
| ldap_search_base          |None      |                                                                    |
| ldap_uri                  |None      |                                                                    |
| ldap_users                |None      | list of users to be added to the access filter whitelist           |
| ldap_groups               |None      | list of groups to be added to the access filter whitelist          |
| usernames_case_sensitive  |True      | bool determining whether username queries should be case sensitive |

## Dependencies

None

## Example Playbook
```
- hosts: servers
  roles:
    - role: gabethecabbage.sssd-ldap
      ldap_schema: rfc2307bis
      ldap_search_base: ou=company,o=co,c=uk
      ldap_uri: ldap.company.co.uk
      usernames_case_sensitive: False
      ldap_users:
        - user1
        - user2
      ldap_groups:
        - cn=group1,ou=groups,ou=company,o=co,c=uk
        - cn=group2,ou=groups,ou=company,o=co,c=uk

```

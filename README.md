# aap-stager
Use Ansible (ansible core) to stage servers for an Ansible Automation Platform install.

## Pre-requisites
The hosts you're targeting must be installed with RHEL 7 or RHEL 8 and must be
registered. You can register directly to RHSM or to a Satellite. The hosts
must have access to the automation hub repository
(automation-hub-4.2-for-rhel-8-x86_64-rpms or the RHEL 7 equivalent).

## Variables

| Variable | Definition |
| ---------- | -------- |
| automation_platform_db_managed | If false, we will set up a PostgreSQL machine with the `externaldb` role. If true, we let the AAP installer set up PostgreSQL for us. |
| automation_platform_setup | Base name of the installer bundle filename minus the `.tar.gz`. |
| controller_db_user | An optional username to use for the Controller connections to PostgreSQL. |
| pah_db_user | An optional username to use for the Private Automation Hub connections to PostgreSQL. If you are using the same database for both Controller and PAH, this should be the same username as `controller_db_user`. |
| controller_db_pass | Password for the Controller database connection. |
| pah_db_pass | Password for the PAH database connection. |
| ansible_admin_pass | The password to be set for the admin user once AAP is installed. |
| controller_reg_username | The username for authenticating to `registry.redhat.io`. |
| controller_reg_password | The password for authenticating to `registry.redhat.io`. |

## Usage
See the `automationhub.yml` file for usage of these roles

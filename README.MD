These are the Ansible playbooks I use to deploy my lab environments.

Inventory contains a remote host in the lab environment, primarily for remoting tasks that require large file copies

e.g. ansible-playbook deploy_controller.yml -e @my-controller.yml -i inventory

For Pulse Register/De-register, need to obtain JSON Web Token. Log in to CSP org in a web browser, then browse to:

https://portal.avipulse.vmware.com/portal/auth/cspacs?authmode=cspctrlsso

This will return an encrypted JWT that can then be used for the Controller registration/de-registration. The validity lifetime for the JWT is 1 year.

As of October 2023, the above is an undocumented mechanism, so caveat lector!

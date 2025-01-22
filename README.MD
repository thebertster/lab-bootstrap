These are the Ansible playbooks I use to deploy my lab environments.

Inventory contains a remote host in the lab environment, primarily for remoting tasks that require large file copies

e.g. ansible-playbook deploy_controller.yml -e @my-controller.yml -i inventory

Many of the playbooks refer to a specific Controller vars file (as in the above example).

An additional vars file (`site_<site_name>`) contains variables that are common to all Controllers in a given deployment site.

The `<site_name>` is provided in the variable `deployment_site`.

See `site_template.yml` and `controller_template.yml` for templates for these two vars files.

For Pulse Register/De-register, need to obtain JSON Web Token. Log in to CSP org in a web browser, then browse to:

https://portal.avipulse.vmware.com/portal/auth/broadcomtoken

This will return an encrypted JWT that can then be used for the Controller registration/de-registration. The validity lifetime for the JWT is 1 year.

The above is an undocumented mechanism, so caveat lector!

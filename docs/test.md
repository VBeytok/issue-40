---
title: Accessing the Management Console
intro: 'Use the {{ site.data.variables.enterprise.management_console }} to set up and configure {{ site.data.variables.product.product_location }}, schedule maintenance windows, troubleshoot issues, and manage your license.'
redirect_from:
  - /enterprise/admin/articles/about-the-management-console/
  - /enterprise/admin/articles/management-console-for-emergency-recovery/
  - /enterprise/admin/articles/web-based-management-console/
  - /enterprise/admin/categories/management-console/
  - /enterprise/2.9/admin/categories/management-console/
  - /enterprise/2.10/admin/categories/management-console/
  - /enterprise/2.11/admin/categories/management-console/
  - /enterprise/2.12/admin/categories/management-console/
  - /enterprise/admin/articles/accessing-the-management-console/
  - /enterprise/2.9/admin/articles/accessing-the-management-console/
  - /enterprise/2.10/admin/articles/accessing-the-management-console/
  - /enterprise/2.11/admin/articles/accessing-the-management-console/
  - /enterprise/2.12/admin/articles/accessing-the-management-console/
  - /enterprise/admin/guides/installation/web-based-management-console/
  - /enterprise/2.9/admin/guides/installation/web-based-management-console/
  - /enterprise/2.10/admin/guides/installation/web-based-management-console/
  - /enterprise/2.11/admin/guides/installation/web-based-management-console/
  - /enterprise/2.12/admin/guides/installation/web-based-management-console/
productVersions:
  enterprise: '*'
---

### In this guide

- [About the {{ site.data.variables.enterprise.management_console }}](#about-the-management-console)
- [Accessing the {{ site.data.variables.enterprise.management_console }} as a site administrator](#accessing-the-management-console-as-a-site-administrator)
- [Accessing the {{ site.data.variables.enterprise.management_console }} as an unauthenticated user](#accessing-the-management-console-as-an-unauthenticated-user)
- [Unlocking the {{ site.data.variables.enterprise.management_console }} after failed login attempts](#unlocking-the-management-console-after-failed-login-attempts)

### About the {{ site.data.variables.enterprise.management_console }}

Use the {{ site.data.variables.enterprise.management_console }} for basic administrative activities:
- **Initial setup**: Walk through the initial setup process when first launching {{ site.data.variables.product.product_location_enterprise }} by visiting {{ site.data.variables.product.product_location_enterprise }}'s IP address in your browser.
- **Configuring basic settings for your instance**: Configure DNS, hostname, SSL, user authentication, email, monitoring services, and log forwarding on the Settings page.
- **Scheduling maintenance windows**: Take your {{ site.data.variables.product.product_location_enterprise }} offline while performing maintenance using the {{ site.data.variables.enterprise.management_console }} or administrative shell.
- **Troubleshooting**: Generate a support bundle or view high level diagnostic information.
- **License management**: View or update your {{ site.data.variables.product.prodname_enterprise }} license.

You can always reach the {{ site.data.variables.enterprise.management_console }} using {{ site.data.variables.product.product_location_enterprise }}'s IP address, even when the instance is in maintenance mode, or there is a critical application failure or hostname or SSL misconfiguration.

To access the {{ site.data.variables.enterprise.management_console }}, you must use the administrator password established during initial setup of {{ site.data.variables.product.product_location_enterprise }}. You must also be able to connect to the virtual machine host on port 8443. If you're having trouble reaching the {{ site.data.variables.enterprise.management_console }}, please check intermediate firewall and security group configurations.

### Accessing the {{ site.data.variables.enterprise.management_console }} as a site administrator

The first time that you access the {{ site.data.variables.enterprise.management_console }} as a site administrator, you must upload your {{ site.data.variables.product.prodname_enterprise }} license file to authenticate into the app. For more information, see "[Managing your {{ site.data.variables.product.prodname_ghe_server }} license](/enterprise/{{ page.version }}/admin/guides/installation/managing-your-github-enterprise-server-license)."

{{ site.data.reusables.enterprise_site_admin_settings.access-settings }}
{{ site.data.reusables.enterprise_site_admin_settings.management-console }}
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}
{{ site.data.reusables.enterprise_management_console.save-settings }}

### Accessing the {{ site.data.variables.enterprise.management_console }} as an unauthenticated user

1. Visit this URL in your browser, replacing `hostname` with your actual {{ site.data.variables.product.prodname_ghe_server }} hostname or IP address:
  ```shell
http(s)://HOSTNAME/setup
  ```
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}

### Unlocking the {{ site.data.variables.enterprise.management_console }} after failed login attempts

The {{ site.data.variables.enterprise.management_console }} locks after ten failed login attempts are made in the span of ten minutes. You must wait for the login screen to automatically unlock before attempting to log in again. The login screen automatically unlocks as soon as the previous ten minute period contains fewer than ten failed login attempts. The counter resets after a successful login occurs.

To immediately unlock the {{ site.data.variables.enterprise.management_console }}, use the `ghe-reactivate-admin-login` command via the administrative shell. For more information, see "[Command line utilities](/enterprise/{{ page.version }}/admin/guides/installation/command-line-utilities#ghe-reactivate-admin-login)" and "[Accessing the administrative shell (SSH)](/enterprise/{{ page.version }}/admin/guides/installation/accessing-the-administrative-shell-ssh/)."

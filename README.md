# Grafana informations

## Trick 1 : Reset admi pasword
```
grafana-cli admin reset-admin-password --homepath "/usr/share/grafana" --config "/etc/grafana/grafana.ini" admin
```
source link : https://codesposts.com/Wg04jK59

## Trick 2 : No login appear on the grafana interface

To setup login for anonymous users you need to make these small configuration changes in the default.ini/grafana.ini file (Grafana\conf).
If you want to hide the login page do this configuration set disable_login_form and allow anonymous
Do the opposite if you want to activate the login page.

```
    [auth]
    # Set to true to disable (hide) the login form, useful if you use OAuth
    #disable_login_form = false 
    disable_login_form = true

    Change disable_login_form to true.

    Enable anonymous access:

    [auth.anonymous]
    # enable anonymous access 
    enabled = true

    Specify the organization:

    # specify organization name that should be used for unauthenticated users
    org_name = YOUR_ORG_NAME_HERE

    Restart Grafana and you should be able to see the Grafana dashboard. If not, just change your org role from Viewer to Editor:

    # specify role for unauthenticated users
    org_role = Editor
```

Source link : https://stackoverflow.com/questions/33111835/how-to-set-up-grafana-so-that-no-password-is-necessary-to-view-dashboards


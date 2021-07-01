
# ServiceNow SlackAuth proxy

This project is to allow the folks from 
https://sndevs.slack.com to authenticate 
with their Slack account.


## Installation 

Either download the update set XML file from the [ServiceNow Share](https://developer.servicenow.com/connect.do#!/share/contents/1627055_slack_sso_extension?v=1&t=PRODUCT_DETAILS)
or [fork this repo](https://github.com/j4rodm/sn-slackauth-ext) and [install it in Studio](https://docs.servicenow.com/bundle/quebec-application-development/page/build/applications/task/t_ImportAppFromSourceControl.html)

### Setting the System Properties

You'll need to set `x_jarodm_slack_ext.relay.extension_id` and `x_jarodm_slack_ext.relay.extension_token`
to get this working.  To get those go to https://sndevs.slack.com in channel #sndevs_sso_dev and ask for them.


| Property | Value | Notes |
| --- | --- | --- |
| x_jarodm_slack_ext.relay.extension_id    |                                      | Ask for in #slack_sso_extension         |
| x_jarodm_slack_ext.relay.extension_token |                                      | Ask for in #slack_sso_extension         |
| x_jarodm_slack_ext.fqdn                  |                                      | If using custom domain, give FQDN*.     |
| x_jarodm_slack_ext.logging.verbosity     | warn                                 | Log level for local logging	            |
| x_jarodm_slack_ext.log_level.rest	       | basic                                | Log level for outbound API calls.       |	
| x_jarodm_slack_ext.relay.server          | dev56843.service-now.com             | FQDN* of Relay Instance.                |
| x_jarodm_slack_ext.default_user_roles    |                                      | Sysid(s) of roles assigned to new users |	
| x_jarodm_slack_ext.redir_endpoint        | /api/x_jarodm_slack_ext/auth/process | API Endpoint to process auth            |	
| x_jarodm_slack_ext.relay.endpoint        | /api/x_jarodm_slacksso/relay         | API Endpoint of Relay Instance          |

*FQDN** is always the URL without the protocol.  e.g. (example.com, not https://example.com)
## Demo

![](/slack-sso.gif)
  
## Authors

- [@j4rodm](https://www.github.com/j4rodm)

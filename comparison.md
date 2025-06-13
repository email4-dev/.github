# FOSS vs SaaS

| Module          | Solution          | SaaS Only | Description                                                                                                           |
| --------------- | ----------------- | --------- | --------------------------------------------------------------------------------------------------------------------- |
| Mailer Service  | Custom            | No        | An email service that subscribes to the mail queue and processes emails                                               |
| Bouncer Service | Custom            | Yes       | A bouncer service that fetches bounce emails from a designated mailbox and bans recipients to prevent IP blacklisting |
| Mail Queue      | Valkey            | No        | A Redis fork used to pass events and data between the services                                                        |
| Advanced Logs   | ClickHouse        | Yes       | Also enables analytics. In the FOSS version plain console logging is used                                             |
| Anti-Spam       | Rspamd            | Yes       | If your email service already provides a spam filter you probably don't need this                                     |
| API Backend     | Custom            | No        | Handles all form submissions and API requests                                                                         |
| Captcha         | Altcha            | No        | PoW based, zero input captcha. The code is included in the API backend                                                |
| Database & Auth | Pocketbase        | No        | Only the superuser account is used in the FOSS version, no multi-tenancy                                              |
| Dashboard       | Sveltekit         | No        | The FOSS version lacks multi-tenancy, log viewing, and analytics                                                      |

## Email Server / Account
FOSS: BYO (Bring Your Own)
SaaS: High availability Email4.dev email service + BYO, optional backup email server configuration (in case your main server is down)

## Multiple users/tenants
SaaS only

## Logging & Stats
FOSS: Console logs for all services
SaaS: Detailed log filtering and stats via the Dashboard

## Calendar Events
FOSS: standard ics file attachments
SaaS: icalEvent Support (Request / Publish / Cancel)

## List Commands https://nodemailer.com/message/list-headers
SaaS only

## Spam prevention (all are optional)
FOSS: PoW based captcha + honeypot + Domain validation
SaaS: PoW based captcha + honeypot + Domain validation + rspamd Spam Filter + bounce management

## Support
FOSS: [Github Discussions](https://github.com/orgs/email4-dev/discussions) ([issues](https://github.com/email4-dev/.github/issues) are for bugs and feature requests only)
SaaS: Free Ticket/Email Support included in all paid plans, available through the [dashboard](https://my.email4.dev)
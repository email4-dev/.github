# Under Consideration

## Webhooks

Email4.dev solves the problem of using an email service without a backend. That said; I can't say webhooks are totally out of scope. If they enter the roadmap though, we shall only accomodate for custom http webhooks, not direct integrations (e.g. Discord, Teams, Telegram, etc.).

If direct integrations become available via the community (a.k.a. 3rd party contributors), we shall accomodate for them with their own NATS subject and configuration (via the dashboard), but they won't be merged in any Email4.dev repo or be officially supported.

## Server Side Form Submissions

Server-side form submissions, although easily implemented, give no real value to Email4.dev. If this feature enters the roadmap, it will only work with an IP allowlist for security reasons.

# Out of scope

## Bulk/Mass Messaging

This is totally out of scope of Email4.dev. We suggest you run [Listmonk](https://github.com/knadh/listmonk), or [Mautic](https://github.com/mautic/mautic) if you need something more sophisticated. We run Listmonk btw!

### But I just need to get the Email4.dev emails on more than 100 recipients

Practically there's no limit to the recipients, but 100 recipients is a good limit per message and that's what we have implemented. Gmail for instance has a limit of 500 recipients per day (500 messages with 1 recipient, 1 message with 500 recipients, or anything in between).

Our suggestion is to set up an alias/forwarding email address with your provider to handle the forwarding and use only 1 recipient address (the alias) in Email4.dev.
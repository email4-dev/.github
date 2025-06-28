# FAQ

## Altcha is not working, responses arrive already expired or expire too soon (less than a minute)

Make sure your server's time is correct. Install an NTP daemon if you don't have one already, and restart the docker containers.

## Uploaded files show up as regular input fields without attachments

You forgot to add `enctype="multipart/form-data"` to your `<form>` element.

## Why make a SaaS version? Why isn't the X feature free?

Money, we have families to raise. The FOSS version has been carefully assembled to enable individual and small business use where multi-tenancy, advanced logging, and analytics are not crucial.

## Why use Bun?

1. It natively runs Typescript, so no build step needed.
2. Usually is faster than node and less picky with packages than deno.

## What happens if I exceed my SaaS plan?

- You shall receive a warning about it.
- All messages over the daily limit shall overflow to the next day.
- All attachments exceeding the limit will not be attached, there will be a notice about the missing attachment.
- We are not responsible for lost messages due to consecutive days of exceeding your plan's limit.

## Can I self-host the SaaS version?

Sure, enterprise plans are available upon request.
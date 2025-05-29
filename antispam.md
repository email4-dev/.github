Email4.dev uses multiple antispam layers of protection, all configurable and optional.

# Honeypot

When setting up a form handler you can define, or auto-generate, a honeypot field. This field must be present in your form submissions with an empty string or null value.

* If it's not present; you will get an error.
* If it has any non-empty or non-null value; you will get an error.

## Example of honeypot form input

```html
<div style="position: absolute; left: -9999px;" aria-hidden="true">
  <input name="nickname" type="text" value="" />
</div>
```

## Keep in mind

1. Bots may detect random strings, use a real word as input name.
2. Bots do detect hidden or zero dimension fields, `position: absolute; left: -9999px;` in an inline style of the parent element should be safe.

# CAPTCHA

Email4.dev uses [Altcha](https://github.com/altcha-org/altcha) as its CAPTCHA solution. This is a self-hosted single/no click proof of work solution that verifies client requests by calculating a hash on both ends. It is also enabled in the form handler.

## Default configuration

| Key                | Value  | Type       | Description                                                         |
| ------------------ | ------ | ---------- | ------------------------------------------------------------------- |
| CAPTCHA_EXPIRE     | 60     | Seconds    | After how many seconds the altcha challenge expires                 |
| CAPTCHA_COMPLEXITY | 100000 | Iterations | How many iterations should be run to calculate the altcha challenge |

## Altcha Widget Example

Load the official [altcha library](https://altcha.org/docs/v2/widget-integration/), and then use the following code in your form.

```html
<altcha-widget
    style="--altcha-max-width:100%"
    challengeurl="https://YOUR_EMAIL4DEV_DOMAIN/altcha/YOUR_FORM_ID"
    expire="60000"
    maxnumber="100000"
></altcha-widget>
```

## Keep in mind

1. Altcha challenges are deleted from the server upon expiry and upon use (single use only).
2. The Altcha widget will refresh automatically upon expiry. By default it will request a new challenge, disable this with `refetchonexpire="false"`. For more options check the [official documentation](https://altcha.org/docs/v2/widget-integration/#configuration).
3. Although the plain `handler_id` is used as the `hmacKey`, this is only visible to anyone with access to the pocketbase database or logs; plus it's a short UUID, not something easy to guess.
4. Email4.dev only works for front-end requests (HTML forms & Browser fetch), not server-side requests. If you have your own backend, you probably don't need this service.
5. The Altcha server is embedded in the Email4.dev API and will run no matter if you use it or not.

# Domain verification

We use 3 types of domain verification:

## 1. Ownership

A custom TXT DNS record you need to add to your domain for forms to be accepted from it. You can exclude forms by marking them as unprotected.

## 2. SPF

Your domain is checked for SPF DNS record alignment with your email gateway. Misalignment only produces a warning in the dashboard.

## 3. DKIM

Your domain is checked for DKIM DNS record existance. A missing DKIM DNS record only produces a warning in the dashboard.

# Spam Filter

In our SaaS product we have incorporated a pre-trained rspamd instance that checks all form submissions for spam. You can choose between `flag` or `reject` for its action.

# Bounce Management

In our SaaS product we also include a bouncer service that monitors bounces and bans recipient addresses to avoid grey/black lists.
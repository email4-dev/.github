# Email4.dev

**Email4.dev** is a dockerized microservice platform for handling form submissions and sending emails. It's built with modern web technologies, supports both form submissions and frontend fetch requests, and includes a dashboard for managing your data.

There’s a self-hostable FOSS version and a SaaS variant with additional features.

---

## ✨ Features

- 📨 Accept form submissions via plain forms or javascript `fetch()`
- ⚙️ API and mailer written in **TypeScript** using **Bun**
- 📬 Emails processed asynchronously using **NATS**
- 🧾 Simple dashboard built with **SvelteKit**
- 🛡️ Advanced Anti-spam, bouncer, and advanced logging (SaaS only)

---

## 🧱 Architecture

This project is split into microservices:

- **API Backend** – Handles form submissions and API requests.
- **Mailer Service** – Subscribes to the mail queue and sends emails.
- **Mail Queue (NATS)** – Core event system for distributing mail jobs.
- **Dashboard (SvelteKit)** – View submissions, manage forms, configure settings.
- **Database** – Uses **Pocketbase** for auth and persistence.

---

## 🛠️ Tech Stack

| Service         | Tech                                                                                          |
| --------------- | --------------------------------------------------------------------------------------------- |
| API             | [TypeScript](https://github.com/microsoft/TypeScript) + [Bun](https://github.com/oven-sh/bun) |
| Mailer          | [TypeScript](https://github.com/microsoft/TypeScript) + [Bun](https://github.com/oven-sh/bun) |
| Queue           | [NATS](https://github.com/nats-io)                                                            |
| Dashboard       | [SvelteKit](https://github.com/sveltejs/kit)                                                  |
| Database/Auth   | [Pocketbase](https://github.com/pocketbase/pocketbase)                                        |
| Captcha         | [Altcha](https://github.com/altcha-org/altcha-lib)                                            |

---

## Read more

- [🧾 Documentation](https://docs.email4.dev)
- [🔧 Quick Installation](https://github.com/email4-dev/docker)
- [🛡️ Antispam](https://github.com/email4-dev/.github/antispam.md)
- [⚖️ FOSS vs SaaS](https://github.com/email4-dev/.github/comparison.md)
- [📝 TODO](https://github.com/email4-dev/.github/todo.md)
- [💡 Ideas](https://github.com/email4-dev/.github/ideas.md)
- [❓ FAQ](https://github.com/email4-dev/.github/faq.md)

## 📮 Questions?

Use the [issues](https://github.com/email4-dev/.github/issues) to report any bugs, use the [discussions](https://github.com/orgs/email4-dev/discussions) for anything else.

Paid customers can seek help directly on their [dashboard](https://my.email4.dev/)

## 📜 License

Mozilla Public License Version 2.0 for the FOSS version. The SaaS version includes proprietary modules.
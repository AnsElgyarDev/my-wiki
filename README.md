# My Wiki

[![License](https://img.shields.io/github/license/AnsElgyarDev/my-wiki)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/AnsElgyarDev/my-wiki)](https://github.com/AnsElgyarDev/my-wiki/commits/main)
[![Repo Size](https://img.shields.io/github/repo-size/AnsElgyarDev/my-wiki)](https://github.com/AnsElgyarDev/my-wiki)
![Focus](https://img.shields.io/badge/focus-backend%20engineering-blue)
![Stack](https://img.shields.io/badge/stack-ASP.NET%20Core-512BD4)

My personal notes on backend topics I enjoy writing about, tend to forget,
or simply want to have a clear reference for.

Each topic is self-contained: a written explanation, diagrams, and a working
reference implementation.

---

## Table of Contents

- [Motivation](#motivation)
- [Topics](#topics)
- [Repository Structure](#repository-structure)
- [Anatomy of a Topic](#anatomy-of-a-topic)
- [Running the Samples](#running-the-samples)
- [Security Notes](#security-notes)
- [Roadmap](#roadmap)
- [Feedback](#feedback)
- [License](#license)

---

## Motivation

Most of what I learn in backend engineering is learned once, applied for a while, and then partially forgotten until the next project needs it again.

This repository exists to solve that problem. It serves three purposes:

1. **Long-term reference.** Each topic is written once, in my own words, so I can recover the full mental model quickly instead of re-reading documentation from scratch.
2. **Reusable code.** Every topic is backed by a working implementation that can be read, run, and adapted as a utility in other projects.
3. **Engineering portfolio.** The repository is public so that the depth and consistency of the work can be evaluated directly.

Topics are independent of each other. They are chosen based on what I use in real projects, what I tend to forget, and what I want to understand more deeply.

---

## Topics

The table below reflects the current state of the wiki and is updated as work progresses.

| Category | Topic | Status | Last Updated |
|---|---|---|---|
| Authentication | [JWT](auth/jwt) | Complete | 2026-10 |
| Authentication | Refresh Tokens | In Progress | - |
| Authentication | Role-Based Access Control | In Progress | - |
| Authentication | Policy-Based Authorization | Planned | - |
| Authentication | OAuth 2.0 and OpenID Connect | Planned | - |
| AI | MCP (Model Context Protocol) | Planned | - |

**Status definitions**

| Status | Meaning |
|---|---|
| Planned | Identified as a future topic. No content yet. |
| In Progress | Work has started. Content may be incomplete or inaccurate. |
| Complete | Documentation, diagrams, and a working sample are all present and reviewed. |
| Needs Revision | Previously complete, but outdated or flagged for improvement. |

---

## Repository Structure

Topics are grouped into categories. Each topic is a self-contained directory.

```text
my-wiki/
├── README.md
├── LICENSE
├── .gitignore
│
├── auth/
│   ├── jwt/
│   ├── refresh-tokens/
│   ├── role-based-access/
│   └── ...
│
└── mcp/
    └── ...
```

Naming conventions:

- Directories use `lowercase-with-dashes`.
- Categories are top-level directories and contain no files of their own beyond topic folders.
- Every topic directory must contain a `README.md`.

---

## Anatomy of a Topic

Every topic follows the same layout, so the structure is predictable and any topic can be navigated without prior context.

```text
auth/jwt/
├── README.md                   The write-up
├── diagrams/
│   ├── jwt-structure.excalidraw    Editable source
│   ├── jwt-structure.png           Rendered image used in the README
│   └── auth-flow.png
└── src/
    └── JwtDemo/
        ├── JwtDemo.csproj
        ├── Program.cs
        ├── appsettings.json
        ├── Controllers/
        └── Services/
```

| Path | Purpose |
|---|---|
| `README.md` | The explanation. Written to be read top to bottom or used as a quick reference. |
| `diagrams/` | Source files and exported images. Sources are kept so diagrams remain editable. |
| `src/` | A complete, buildable project. Not isolated snippets. |

A topic is considered **Complete** when it explains the problem before the solution, includes at least one diagram, shows the key code as searchable text, ships a project under `src/` that builds without modification, documents trade-offs, and contains no real secrets.

---

## Running the Samples

Prerequisites:

- .NET SDK matching the target framework stated in the topic's README
- Git

```bash
git clone https://github.com/AnsElgyarDev/my-wiki.git
cd my-wiki/auth/jwt/src/JwtDemo
dotnet restore
dotnet run
```

Each sample documents its own configuration, required secrets, and example requests in its topic README.

---

## Security Notes

All samples are written for learning and are not production-ready by default.

- **Secrets are never committed.** Configuration files contain placeholder values only. Real values are supplied through `dotnet user-secrets` or environment variables.
- **Development-only settings are marked.** Options such as `RequireHttpsMetadata = false` are annotated in code and explained in the topic README.
- **Review before reuse.** Anything copied into a production system should be reviewed against current security guidance for your environment.

---

## Roadmap

Planned areas, in rough priority order:

- [x] Authentication fundamentals (JWT)
- [ ] Complete the authentication series (refresh tokens, RBAC, policies, OAuth 2.0)
- [ ] MCP (Model Context Protocol)

The roadmap reflects intent, not commitment, and changes as priorities shift. New topics are added as I come across them in real work.

---

## Feedback

Corrections and suggestions are welcome. If you find an inaccuracy, an outdated practice, or a better approach, open an [issue](https://github.com/AnsElgyarDev/my-wiki/issues) describing the topic and the problem.

---

## License

Distributed under the terms of the license in the [LICENSE](LICENSE) file.

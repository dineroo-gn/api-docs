# 📘 Dineroo API Documentation

Welcome to the OpenAPI documentation for the **Dineroo** project, which centralizes all the REST API specifications used by client applications (mobile, admin, etc.).

This documentation is automatically **bundled** and published on **GitHub Pages** after each spec update.

---

## 📂 Project structure

```
API-DOCS/
├── .github/
│   └── workflows/
│       └── bundle-docs.yml          # GitHub Action to bundle automatically
├── docs/
│   ├── index.html                   # Redoc viewer (display on GitHub Pages)
│   ├── openapi/
│   │   ├── bundle.yaml              # Automatically generated file
│   │   ├── openapi.yaml             # OpenAPI master file (entry point)
│   │   ├── paths/                   # API routes
│   │   │   ├── users.yaml
│   │   │   ├── orders.yaml
│   │   │   └── restaurants.yaml
│   │   └── components/
│   │       ├── responses/
│   │       │   └── ErrorResponse.yaml
│   │       └── schemas/
│   │           ├── Menu.yaml
│   │           ├── User.yaml
│   │           ├── OrderResponse.yaml
│   │           └── ...
├── node_modules/
├── package.json                     # `bundle-docs` script with redocly
├── package-lock.json
├── .gitignore
└── README.md

```

---

## 🛠️ Development

### Prerequisites

- Node.js ≥ 18
- `npm install` to install local dependencies (`@redocly/cli`)

### Bundle documentation

```bash
npm run bundle-docs
```

This generates a `docs/openapi/bundle.yaml` file from `openapi.yaml` and the `paths/` and `components/` files.

---

## 🌐 Preview locally

You can view your documentation locally with a static :

```bash
npm rn serve
```

Then open in your browser :  
http://localhost:3000

> The `docs/index.html` file uses [Redoc](https://redoc.ly/) to display the `bundle.yaml` file.
---

## 🚀 Automatic deployment (GitHub Pages)

At each `push` on the `main` branch, a GitHub Actions workflow:

- Bundle the OpenAPI spec
- Commit the updated `bundle.yaml
- The site is served automatically via GitHub Pages

📄 **URL of doc**:  
`https://dineroo-gn.github.io/api-docs/`

---

## ✅ Conventions

- Always modify `openapi.yaml` or the files in `paths/` or `components/`.
- Never modify manually `bundle.yaml`**, it is generated automatically
---

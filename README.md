<h1 align="center">
    <img src="/.github/assets/logo.svg"
    width="200px"
    alt="Logo" />
</h1>

<h3 align="center">
  SaaS Next.js RBAC
</h3>

<p align="center">
  :lock: Application with all the necessary elements to configure a multi-tenant SaaS with Next.js, including RBAC authentication and authorization
</p>
    
<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/osvaldokalvaitir/saas-nextjs-rbac.svg?color=00A83A">

  <img alt="GitHub language top" src="https://img.shields.io/github/languages/top/osvaldokalvaitir/saas-nextjs-rbac.svg?color=00A83A">

  <a href="https://kalvaitir.com/">
    <img alt="Made by Kalvaitir" src="https://img.shields.io/badge/made%20by-Kalvaitir-00A83A">
  </a>

  <img alt="License" src="https://img.shields.io/badge/license-MIT-00A83A">
</p>

<p align="center">
  <a href="#computer-demo">Demo</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<a href="#clipboard-features">Features</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<a href="#wrench-install-and-run">Install and run</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<a href="#memo-license">License</a>
</p>

## :computer: Demo

<p align="center">
  <img src="/.github/assets/demo.gif" alt="Demo" />
</p>

## :clipboard: Features

### Authentication

- [x] It should be able to authenticate using e-mail & password;
- [x] It should be able to authenticate using Github account;
- [x] It should be able to recover password using e-mail;
- [x] It should be able to create an account (e-mail, name and password);

### Organizations

- [x] It should be able to create a new organization;
- [x] It should be able to get organizations to which the user belongs;
- [x] It should be able to update an organization;
- [x] It should be able to shutdown an organization;
- [x] It should be able to transfer organization ownership;

### Invites

- [x] It should be able to invite a new member (e-mail, role);
- [x] It should be able to accept an invite;
- [x] It should be able to revoke a pending invite;

### Members

- [x] It should be able to get organization members;
- [x] It should be able to update a member role;

### Projects

- [x] It should be able to get projects within a organization;
- [x] It should be able to create a new project (name, url, description);
- [x] It should be able to update a project (name, url, description);
- [x] It should be able to delete a project;

### Billing

- [x] It should be able to get billing details for organization ($20 per project / $10 per member excluding billing role);

## RBAC

Roles & permissions.

### Roles

- Owner (count as administrator)
- Administrator
- Member
- Billing (one per organization)
- Anonymous

### Permissions table

|                          | Administrator | Member | Billing | Anonymous |
| ------------------------ | ------------- | ------ | ------- | --------- |
| Update organization      | ✅            | ❌     | ❌     | ❌        |
| Delete organization      | ✅            | ❌     | ❌     | ❌        |
| Invite a member          | ✅            | ❌     | ❌     | ❌        |
| Revoke an invite         | ✅            | ❌     | ❌     | ❌        |
| List members             | ✅            | ✅     | ✅     | ❌        |
| Transfer ownership       | ⚠️            | ❌     | ❌     | ❌        |
| Update member role       | ✅            | ❌     | ❌     | ❌        |
| Delete member            | ✅            | ⚠️     | ❌     | ❌        |
| List projects            | ✅            | ✅     | ✅     | ❌        |
| Create a new project     | ✅            | ✅     | ❌     | ❌        |
| Update a project         | ✅            | ⚠️     | ❌     | ❌        |
| Delete a project         | ✅            | ⚠️     | ❌     | ❌        |
| Get billing details      | ✅            | ❌     | ✅     | ❌        |
| Export billing details   | ✅            | ❌     | ✅     | ❌        |

> ✅ = allowed
> ❌ = not allowed
> ⚠️ = allowed w/ conditions

#### Conditions

- Only owners may transfer organization ownership;
- Only administrators and project authors may update/delete the project;
- Members can leave their own organization;

## :wrench: Install and run

Open terminal:

```sh
# Clone this repo
git clone https://github.com/osvaldokalvaitir/saas-nextjs-rbac

# Entry in folder
cd saas-nextjs-rbac

# Install deps with pnpm
pnpm install

# Launch the app with pnpm
pnpm dev
```

Click to learn more about the tools used:  [Docker](https://github.com/osvaldokalvaitir/awesome/blob/main/src/containers/docker.md), [PostgreSQL Docker Image bitnami-postgresql](https://github.com/osvaldokalvaitir/awesome/blob/main/src/containers/docker/images/bitnami-postgresql.md), [Neon](https://github.com/osvaldokalvaitir/awesome/blob/main/src/sgdbs/postgresql/neon.md), [Insomnia](https://github.com/osvaldokalvaitir/awesome/blob/main/src/api-clients/insomnia.md), [Git](https://github.com/osvaldokalvaitir/awesome/blob/main/src/version-controls/git.md), [GitHub](https://github.com/osvaldokalvaitir/awesome/blob/main/src/version-controls/git/tools/github.md), [GitHub Actions](https://github.com/osvaldokalvaitir/awesome/blob/main/src/ci-cd/github-actions.md), [Render](https://github.com/osvaldokalvaitir/awesome/blob/main/src/ci-cd/render.md), [Vercel](https://github.com/osvaldokalvaitir/awesome/blob/main/src/paas/vercel.md).

[![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=SaaS%20Next.js%20RBAC%20API&uri=https%3A%2F%2Fgithub.com%2Fosvaldokalvaitir%2Fsaas-nextjs-rbac%2Fblob%2Fmain%2FInsomnia.json)

## :memo: License

This project is under the MIT license. See [LICENSE](/LICENSE) for more information.

---

<p align="center">
Developed with 💚 by <a href="https://www.linkedin.com/in/osvaldokalvaitir">Osvaldo Kalvaitir Filho</a>
</p>

# NestJS + NextJS Monorepo Template

This monorepo template utilises [yarn workspaces](https://classic.yarnpkg.com/lang/en/docs/workspaces/) to manage package dependencies under a single `yarn.lock` file.

---

## Installing

Run a single `yarn` command at the root level, yarn workspaces will install all necessary dependencies in each
workspace, with a main `node_modules` at the root level.

---

## Running Local Development

You can run either the client or server using a `yarn workspace` command that can run any script from any workspace.

```bash
yarn workspace client dev
yarn workspace server start:dev
```

---

## Add New Workspaces

Additional workspaces for shared libraries or components can be created at the root level, simply add the new workspace into the `package.json`

```json
{
  "private": true,
  "name": "nestjs-auth-with-refresh-jwt",
  "workspaces": [
    "client",
    "server"
    // add the new workspace here
  ]
  //...
}
```

---

## NOTES

- By default, running `yarn create next-app --typescript` does not include a `version` property in the `package.json`, which is necessary for `yarn workspaces` to detect a valid workspace.

- NestJS was installed using the CLI command `nest new server --skip-git`

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img src="assets/logo-light.svg" alt="yggy" height="56">
  </picture>
</p>

<h1 align="center">yggy SDK for TypeScript and JavaScript</h1>

<p align="center">Typed client for the yggy API. Works in Node.js 18+ and in the browser (fetch).</p>

## Install

The npm package `@yggy-tech/sdk` is not published yet. Until it is, install from GitHub:

```bash
npm install github:yggy-tech/yggy-sdk-js
```

## Example

List the projects your key can see:

```ts
import { Configuration, ProjectsApi } from "@yggy-tech/sdk";

const config = new Configuration({
  basePath: "https://api.yggy.tech",
  apiKey: process.env.YGGY_API_KEY,
  headers: { "x-yggy-organization-id": "acme-corp" },
});

const { projects } = await new ProjectsApi(config).listProjects();
for (const project of projects) console.log(project.name);
```

## Authenticate

Create an API key in yggy under **Developers → API keys** and keep it in an environment variable. A key that belongs to one organization needs nothing else. A personal key can see several organizations, so name the one you want in the `x-yggy-organization-id` header, by id or slug, as the example does.

See [Authentication](https://docs.yggy.tech/developers/authentication/) for key types and permissions.

## What you can call

Projects, documents (upload, status, extracted facts, download, retry), questions over a project or a whole organization, chat, entity lookup by identity, the ontology overview and graph exports. The [API reference](https://docs.yggy.tech/developers/rest/reference/) lists every operation with its parameters. For a first walkthrough, follow the [quickstart](https://docs.yggy.tech/developers/quickstart/).

## Generated code

Everything except this file is generated from the yggy OpenAPI document, so a change here is overwritten by the next sync. Report bugs or request an operation by opening an issue in this repository, or write to [support](https://yggy.tech/support).

## License

Apache-2.0. See [LICENSE](LICENSE).

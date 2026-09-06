# @8th-dev/ui

A React UI component library built with shadcn/ui, Tailwind CSS, and TypeScript.

## Tech Stack

- React — UI framework
- TypeScript — Type safety
- Tailwind CSS — Styling
- shadcn/ui — Component primitives (Radix UI)
- tsup — Build tool

## Installation

```bash
pnpm add @8th-dev/ui
```

Import components and the shared stylesheet:

```tsx
import { Button } from "@8th-dev/ui"
import "@8th-dev/ui/styles"
```

## Development

Setup:

pnpm install

Build:

pnpm build

Watch mode:

pnpm dev

Add a shadcn component:

pnpm dlx shadcn@latest add button

## Publishing

For a local release, update the version in `package.json`, then run:

```bash
npm login
npm whoami
pnpm install --frozen-lockfile
pnpm build
npm publish --access public
```

`npm whoami` should show an npm account with permission to publish the
`@8th-dev/ui` package. npm does not allow publishing the same version twice.

To publish from GitHub Actions instead, commit the version change and push a
matching tag. For example, version `0.2.1` requires tag `v0.2.1`:

```bash
git tag v0.2.1
git push origin v0.2.1
```

The repository's Actions secrets must include `NPM_TOKEN`, containing an npm
access token with read and write permission for `@8th-dev/ui`. Logging in with
`npm login` locally does not authenticate GitHub Actions.

## Project Structure

8-ui/
├── src/
│   ├── components/
│   │   └── ui/
│   ├── styles/
│   │   └── globals.css
│   └── index.ts
├── dist/
├── package.json
├── tsup.config.ts
├── tailwind.config.js
└── components.json

## Adding New Components

1. Add a shadcn component: pnpm dlx shadcn@latest add button
2. Rebuild: pnpm build
3. Release a new package version, then update your consuming app with `pnpm update @8th-dev/ui`

## Customizing Components

You own all component code. Modify src/components/ui/*.tsx freely.

## Consuming the Library

In your Next.js app layout:

import "@8th-dev/ui/styles"

In your pages:

import { Button } from "@8th-dev/ui"

export default function Home() {
  return <Button variant="outline">Click me</Button>
}

## License

MIT
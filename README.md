# @8th/ui

A private React UI component library built with shadcn/ui, Tailwind CSS, and TypeScript.

## Tech Stack

- React — UI framework
- TypeScript — Type safety
- Tailwind CSS — Styling
- shadcn/ui — Component primitives (Radix UI)
- tsup — Build tool

## Installation

Configure GitHub Packages for the `@8th` scope in the consuming project's `.npmrc`:

```text
@8th:registry=https://npm.pkg.github.com/
```

Authenticate with a GitHub personal access token that has `read:packages`:

```bash
npm login --registry=https://npm.pkg.github.com/ --scope=@8th
```

This stores the credential in your user-level npm configuration, not in the repository. Then install the package:

```bash
pnpm add @8th/ui
```

Import components and the shared stylesheet:

```tsx
import { Button } from "@8th/ui"
import "@8th/ui/styles"
```
import "@8th/ui/styles"

## Development

Setup:

pnpm install

Build:

pnpm build

Watch mode:

pnpm dev

Add a shadcn component:

pnpm dlx shadcn@latest add button

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
3. Release a new package version, then update your consuming app with `pnpm update @8th/ui`

## Customizing Components

You own all component code. Modify src/components/ui/*.tsx freely.

## Consuming the Library

In your Next.js app layout:

import "@8th/ui/styles"

In your pages:

import { Button } from "@8th/ui"

export default function Home() {
  return <Button variant="outline">Click me</Button>
}

## License

Private — for internal use only.
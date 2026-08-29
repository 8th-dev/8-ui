# @8th/ui

A private React UI component library built with shadcn/ui, Tailwind CSS, and TypeScript.

## Tech Stack

- React — UI framework
- TypeScript — Type safety
- Tailwind CSS — Styling
- shadcn/ui — Component primitives (Radix UI)
- tsup — Build tool

## Installation

Since this is a private library, link it locally in your consuming project:

In your app's package.json, add:

{
  "dependencies": {
    "@8th/ui": "file:../8-ui"
  }
}

Then run:

pnpm install

Import components:

import { Button } from "@8th/ui"
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
3. Update your consuming app: cd ../8-web && pnpm install

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
# Platform Monorepo

This monorepo is structured for scalable development using [pnpm](https://pnpm.io/) and [Turbo](https://turbo.build/). It includes multiple apps and shared packages.

## Apps

- **server**: Backend/server-side application ([apps/server](apps/server))
- **web**: Frontend Next.js application ([apps/web](apps/web))

## Packages

- **design-system**: Shared UI components and styles ([packages/design-system](packages/design-system))
- **eslint-config**: Shared ESLint configuration ([packages/eslint-config](packages/eslint-config))
- **types**: Shared TypeScript types ([packages/types](packages/types))
- **typescript-config**: Shared TypeScript configuration ([packages/typescript-config](packages/typescript-config))

## Prerequisites

- [Node.js](https://nodejs.org/) (v18+ recommended)
- [pnpm](https://pnpm.io/) (v8+ recommended)

## Setup

1. **Install dependencies:**
   ```sh
   pnpm install
   ```

2. **Development scripts:**
   - Start all apps in development mode:
     ```sh
     pnpm dev
     ```
   - Build all apps and packages:
     ```sh
     pnpm build
     ```
   - Run tests:
     ```sh
     pnpm test
     ```

3. **Running individual apps:**
   - **Web app:**
     ```sh
     pnpm --filter web dev
     ```
   - **Server app:**
     ```sh
     pnpm --filter server dev
     ```

## Monorepo Tools

- **Turbo**: Used for task orchestration and caching ([turbo.json](turbo.json))
- **pnpm workspaces**: Manages dependencies and linking ([pnpm-workspace.yaml](pnpm-workspace.yaml))

## Adding Components

To add UI components to your app, run:
```sh
pnpm dlx shadcn@latest add button -c packages/design-system
```
Components will be placed in `packages/ui/src/components`.

## Tailwind

Tailwind is preconfigured. See `tailwind.config.ts` and `globals.css` for setup.

## Notes

- All build outputs and caches are ignored via [.gitignore](.gitignore).
- See each app/package for more specific documentation.

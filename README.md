# Bun Monorepo Example

This repository demonstrates a minimal monorepo structure using [Bun](https://bun.com). It showcases how to organize shared packages and applications within a single workspace.

## Project Structure

The monorepo is organized into workspaces defined in `package.json`:

### Apps (`/apps`)

- **web**: A React 19 frontend application.
  - Built directly with Bun (no Vite/Next.js required for this simple setup).
  - Uses Tailwind CSS v4.
  - Consumes the shared `agent` package.
- **cli**: A simple command-line interface application.

### Packages (`/packages`)

- **agent**: A shared library package designed to be consumed by applications in the monorepo.

## Getting Started

### Prerequisites

- [Bun](https://bun.com) (v1.0 or later)

### Installation

Install dependencies for all workspaces from the root:

```bash
bun install
```

## Usage

### Running the Web App

To start the web development server (with hot reloading):

```bash
bun run dev:web
```

Or run directly from the app directory:

```bash
cd apps/web
bun run dev
```

### Running the CLI

```bash
cd apps/cli
bun run start
```

## Key Features

- **Bun Workspaces**: Dependencies are hoisted and shared where possible.
- **Workspace Protocol**: Internal packages are referenced using `workspace:*` (e.g., in `apps/web/package.json`).
- **Fast Tooling**: Uses Bun for package management, bundling, and running scripts.

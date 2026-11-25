# GPUWatch

Explore historical CPU and GPU telemetry, adjust alert thresholds, and export a monitoring report.

[Live demo](https://paragjindal.com/lab/gpuwatch) · [Technical case study](docs/projects/gpuwatch.md)

![GPUWatch concept artwork](docs/artwork.webp)
*Concept artwork*

![GPUWatch running in the integrated engineering lab](public/lab-screenshots/gpuwatch.webp)

## Run independently

Use Node.js 24 or later from the extracted package. npm installs React and Vite from their pinned registry dependencies and the simulator from its included archive.

```sh
npm ci
npm run dev
```

Open [http://localhost:5173](http://localhost:5173). Run `npm test` for the package regression suite and `npm run build` for a static production bundle.

To use Docker, build with `docker build -t gpuwatch .` and run with `docker run --rm -p 127.0.0.1:4173:80 gpuwatch`. The static browser application is served on port 4173.

## Architecture

```mermaid
flowchart LR
  U[Browser controls] --> A[React project]
  A --> D[Project-specific logic]
  S[Versioned simulation package] --> A
  D --> O[Views and local exports]
```

The browser uses synthetic demonstration data. Optional local adapters are documented in the case study. The archive retains its source, tests, installation lock, and GitHub Actions configuration. This source export can be kept in its own repository. A dedicated remote and a redistribution license have not been declared.

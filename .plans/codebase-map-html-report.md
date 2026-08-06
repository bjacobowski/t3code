# Plan: T3 Code codebase map and HTML technical report

## Goal

Create a self-contained HTML report for a developer who is new to T3 Code. The report will explain the repository structure, runtime architecture, important data/control flows, major dependencies, development/build/test tooling, and practical navigation guidance. Findings will be grounded in current source files rather than only restating existing documentation.

## Investigation

1. Read the repository's architecture and glossary documentation, following relevant internal cross-references.
2. Inventory every workspace package and application from its manifest and source entry points.
3. Trace representative end-to-end flows through:
   - web/mobile/desktop clients,
   - shared client runtime,
   - contracts and WebSocket transport,
   - server command/event/projector/reactor pipeline,
   - provider adapters and subprocess management,
   - persistence, authentication, remote/tunnel paths, and checkpoint/version-control behavior.
4. Inspect build, test, lint, release, native, infrastructure, and development-runner configuration.
5. Generate a direct workspace dependency graph from package manifests and distinguish internal dependencies from major third-party technology choices.
6. Cross-check architectural claims against representative source files and record concrete file paths for further reading.

## Deliverable

Create `.plans/t3-code-codebase-report.html` as a portable, self-contained HTML file with embedded CSS and minimal JavaScript. It will include:

- executive summary and architectural principles,
- repository/workspace map,
- runtime topology and component responsibilities,
- request/command/event/projection/receipt/checkpoint flow,
- provider integration model,
- web, desktop, and mobile client design,
- persistence, networking, auth, and remote-access model,
- dependency and tooling overview,
- testing and development workflows,
- extension/change guides (where to start for common tasks),
- risks, complexity hotspots, and design observations,
- a source index linking every major finding to repository paths.

The visual direction will be an information-dense engineering field guide: restrained, high-contrast, accessible, responsive, printable, and easy to scan. It will not load external assets or modify product code.

## Expected repository changes

- `.plans/codebase-map-html-report.md` — this approved plan.
- `.plans/t3-code-codebase-report.html` — final report.

No application source, configuration, generated dependency lockfiles, or user data will be changed.

## Verification

- Validate that the HTML has balanced structure and no external asset requirements.
- Check all cited repository paths exist.
- Compare the package/dependency summary to workspace manifests.
- Open the report only if browser use is explicitly approved; otherwise perform static validation without launching a browser.

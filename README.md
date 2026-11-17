# FORMA — web release

Production: https://ivanovux.github.io/forma-gym-pages/

This public repository contains only the exported web application and publishing workflows. Editable source is maintained separately in the private `ivanovux/forma-gym` repository. User records and private backups are never stored here.

## Release

`release-manifest.json` records the SHA-256 of each `web-release-*.zip`. The Pages workflow verifies these checksums, extracts the static site, and deploys it through GitHub Actions. A separate live verification workflow compares every served release file with the archive contents.

The application uses the existing Supabase authentication and database. Moving the web host does not move or replace account records. Sign-in uses an email code.

Build for `/forma-gym-pages` with `FORMA_BASE_PATH=/forma-gym-pages`. Keep the public Supabase client configuration in the build environment; never include server credentials, local environment files, source archives, source maps, or account backups in this repository.

## Verified release — 2026-11-17

- Private source CI: type checking and 118 automated tests passed.
- Isolated backup checks: saved workouts, history, favorites, settings and achievements retained; workout execution, cloud save/reload, PDF export and new sharing URLs verified.
- Published resources: complete checksum verification passed.
- Account owner confirmed successful email sign-in and existing workouts, history and statistics at the new address.

Old shared URLs, guest state and unfinished sessions are outside the migration scope by owner instruction.

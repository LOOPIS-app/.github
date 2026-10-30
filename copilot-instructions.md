# CoPilot Instructions

> Authored by CoPilot; this document is a work in progress and should be completed as repository knowledge grows.

## LOOPIS Components

### 1. WordPress installation

- **WordPress Multisite** - Network providing a LOOPIS.app main site and subsites for each LOOPIS area/locker.

### 2. WordPress themes

- **LOOPIS Theme HQ** - Theme providing frontend for LOOPIS.app main page.
- **LOOPIS Theme** - Theme providing frontend for LOOPIS.app/subsites.

### 3. WordPress plugins

- **LOOPIS Admin** - Plugin for configuring the WP Admin area of LOOPIS.app.
- **LOOPIS Config** - Plugin for configuring the WP installation of LOOPIS.app.
- **LOOPIS Content** - Plugin for configuring the post content of LOOPIS.app.
- **LOOPIS Cronjobs** - Plugin for configuring the cronjobs of LOOPIS.app.
- **LOOPIS Develoopers** - Plugin providing tools for developing and testing LOOPIS.app.
- **LOOPIS Users** - Plugin for configuring user management in LOOPIS.app.

### 4. WordPress MU-plugins

- **LOOPIS Constants** - Definitions of shared path/URL constants for LOOPIS components.
- **LOOPIS Environment** - Definitions of environment variables from `.env` file, for development purposes.
- **LOOPIS Log** - Configuration of details, timestamp and filter for `debug.log`.

## Architecture

- LOOPIS.app is a WordPress Multisite network.
- Two separate WordPress themes owns presentation and frontend behavior: `LOOPIS Theme` serves subsites and shares frontend assets, while `LOOPIS Theme HQ` adds main-site functionality.
- Six WordPress plugins customise the default handling of content, users, WP Admin Area and scheduled jobs.
- MU-plugins load early to provide shared path/URL constants, development environment values, and logging.
- `LOOPIS Config` provisions/configures the WordPress installation and manages component deployment.
- See the [development guide](./resources/development-guide.md) and [local setup](./resources/local-setup.md) for the full component overview and environment setup.

## Build and test

- Develop and validate the integrated application in Local WP; use the LOOPIS Config plugin to install/configure components, then verify behavior in the browser.
- No common build, test suite, or lint command is configured across the component repositories. For a PHP syntax check, run `php -l path/to/file.php` from the relevant component root; there is no standard single-test command.

## Conventions

- The application spans separate repositories for each component. Make changes in the owning component and follow its existing structure and entry points; use the shared development guide and component READMEs when a change crosses boundaries.
- Prefer WordPress hooks and the component's established loading patterns. Shared runtime paths/URLs are supplied by the `LOOPIS Constants` MU-plugin; reuse those constants rather than hard-coding installation paths.
- Keep subsite and main-site theme responsibilities separate. Shared theme assets must remain compatible with both themes.

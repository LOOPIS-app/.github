# LOOPIS Development Guide

This guide is designed for developers who are new to PHP and WordPress. It provides an overview of the LOOPIS project structure, essential WordPress concepts, and debugging setup to help you get started quickly.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Repository Overview](#repository-overview)
- [WordPress Basics](#wordpress-basics)
- [Debugging Setup](#debugging-setup)

## Prerequisites

1. Follow the [local setup guide](https://github.com/LOOPIS-app/.github/blob/main/guides/local-setup.md) to install and run LOOPIS locally.
2. **Important Note**: In a WordPress Multisite installation, the Plugins menu in the Dashboard does not have an "Add Plugin" submenu. To add new plugins, navigate to **My Sites > Network Admin > Plugins** instead.

### Development Workflow: Using Symlinks

Instead of downloading the plugin/theme as a ZIP file and uploading it through the Dashboard (as described in the local setup guide), you can use symlinks for a more efficient development workflow:

```bash
# Navigate to your LocalWP plugins directory
cd ${HOME}/Local Sites/loopis/app/public/wp-content/plugins/

# Remove the uploaded plugin folder and create a symlink to your local Git repository
rm -rf loopis-config
ln -s /path/to/your/loopis-config-repo loopis-config
```

**Benefits:**
- Changes in your local Git repository are immediately reflected in WordPress
- No need to re-upload after each code change
- Easier debugging and testing


After creating the symlink, activate the plugin through the WordPress Dashboard as usual.

## Repository Overview

LOOPIS consists of several repositories, each serving a specific purpose:

| Repository | Type | Description |
|------------|------|-------------|
| [loopis-config](https://github.com/LOOPIS-app/loopis-config) | Plugin | Central configuration management - initializes database tables, manages plugins and themes |
| [loopis-admin](https://github.com/LOOPIS-app/loopis-admin) | Plugin | Adds Locker management menu and functionality to WordPress admin dashboard |
| [loopis-theme](https://github.com/LOOPIS-app/loopis-theme) | Theme | Custom WordPress theme for LOOPIS |


### loopis-config Details

**loopis-config** is the central configuration plugin. When activated, it:

1. Logs activation events to `logs/php/error.log` via `loopis_log_on_activation`
2. Initializes database tables by including `functions/db-setup/loopis_config_table.php`
3. Calls `loopis_config_table_insert()` and `loopis_config_reconcile_table()` to set up required data

### loopis-admin Details

**loopis-admin** provides Locker management features in the WordPress admin:

- `interface/` - Handles menu routing and admin interface setup
- `pages/` - Contains the actual page content and functionality

## WordPress Basics

### Plugin Loading Mechanism

WordPress discovers plugins by scanning for files containing "Plugin Name: " in their header comments. This file serves as the plugin entry point. For example, in `loopis-config`, the entry point is `loopis-config.php`.

### Plugin Execution Model

Plugins register callbacks for various WordPress lifecycle events using built-in functions:

- `register_activation_hook` - Called when the plugin is activated
- `add_action` - Hooks into WordPress actions triggered during page loads

### Theme Loading Mechanism

WordPress discovers themes similarly to plugins. It looks for files containing "Theme Name: " in their header comments. For `loopis-theme`, this entry point is `style.css`.

## Debugging Setup

### Prerequisites

1. Enable Xdebug in the LocalWP client
2. Install the following VS Code extensions:
   - PHP Debug
   - PHP Intelephense
   - WordPress Snippets (optional)

### VS Code Configuration

Create a `.vscode/launch.json` file in your project with the following content:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Listen for Xdebug",
            "type": "php",
            "request": "launch",
            "port": 9003,
            "pathMappings": {
                "${env:HOME}/Local Sites/loopis/app/public/wp-content/plugins/loopis-config": "${workspaceFolder}/loopis-config"
            }
        }
    ]
}
```

**Note**: Adjust the `pathMappings` to match your LocalWP site path and the specific plugin/theme you want to debug.

## Getting Started

After setting up your local environment:

1. Start by exploring the [loopis-config](https://github.com/LOOPIS-app/loopis-config) repository - it handles core initialization
2. Review the folder structure in each repository to understand the code organization
3. Use the debugging setup above to step through code and understand the flow

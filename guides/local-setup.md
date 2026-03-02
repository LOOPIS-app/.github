# Local setup of LOOPIS.app

Step-by-step instructions for setting up LOOPIS.app locally.

## 1. Set up your IDE workspace

1. Start [Visual Studio Code](https://code.visualstudio.com/) (or your preferred IDE).
2. Download the folders below to your local drive and add them to your IDE workspace:

| Component | Folder name | Description |
|---|---|---|
| [LOOPIS plugins](https://github.com/orgs/LOOPIS-app/repositories) | `loopis-xxx` | WP plugins |
| [LOOPIS theme](https://github.com/LOOPIS-app/loopis-theme) | `loopis-theme` | WP theme |
| [WordPress stubs](https://github.com/php-stubs/wordpress-stubs) | `wordpress-stubs-x.x.x` | WP functions |
| [WPUM](https://github.com/WPUserManager/wp-user-manager/releases) | `wp-user-manager` | WP user manager plugin |

## 2. Install WordPress development tool

1. Download and install [Local WP](https://localwp.com/) (available for macOS, Windows, and Linux).
2. Open Local WP and click "Add new site" to configure a local installation of WordPress.
3. Use a terminal to create **symbolic links**[^1] for the LOOPIS component folders in your workspace and place the links in the Local WP folders listed below:

| Folder name | Symbolic link location |
|---|---|
| `loopis-config` | `...app/public/wp-content/plugins/` |
| `loopis-develooper` | `...app/public/wp-content/plugins/` |
| `loopis-admin` | `...app/public/wp-content/plugins/` |
| `loopis-content` | `...app/public/wp-content/plugins/` |
| `loopis-mu-plugins` | `...app/public/wp-content/mu-plugins/` |
| `loopis-theme` | `...app/public/wp-content/themes/` |

[^1]: Command for creating symbolic links:
`ln -s /path/to/original /path/to/symlink`

## 3. Run LOOPIS configuration

1. Open the **WP Admin** view of your local WordPress installation.
2. Go to **Plugins** and activate **LOOPIS Config**.
3. In the sidebar, open **LOOPIS Config** and start the LOOPIS configuration.
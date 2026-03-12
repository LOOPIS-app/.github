# 🌱 Local setup of LOOPIS.app

Step-by-step instructions for setting up LOOPIS.app locally.

## 1. Install WP development tool

1. Download and install [Local WP](https://localwp.com/) (available for macOS, Windows, and Linux).
2. Open **Local WP** and click the **+** ("Add new site") to configure a local installation of WordPress.
3. Keep the suggested settings and name your site "LOOPIS".
4. On the last screen (where you set your username, password, and email), click **Advanced options** and set **Is this a WordPress Multisite?** to "Yes - Subdirectory".

## 2. Run LOOPIS configuration plugin

1. Download [loopis-config](https://github.com/LOOPIS-app/loopis-config) as a `.zip` archive and keep it compressed.
2. Open **Local WP** and click **WP Admin** to access the admin area of your local site.
3. Go to **My Sites > Network Admin > Plugins** and click **Add plugin > Upload plugin > Choose file** to install and activate **LOOPIS Config**.
4. In the sidebar, you should now see an item named **LOOPIS Config**. Click it and run the configuration to install all LOOPIS components.

## 3. Set up your IDE workspace

1. Start [Visual Studio Code](https://code.visualstudio.com/) (or your preferred IDE).
2. Consider installing these extensions: **PHP Intelephense + PHP Debug + WordPress Snippets**.
3. Move the folders of the LOOPIS components you wish to review or develop to your IDE workspace.
4. Use a terminal to create **symbolic links**[^1] for the folders you moved, and place those links in the Local WP folders:

| Folder name | Symbolic link location |
|---|---|
| loopis-theme | `...app/public/wp-content/themes/` |
| loopis-<plugin-name> | `...app/public/wp-content/plugins/` |
| loopis-mu-plugins | `...app/public/wp-content/mu-plugins/` |

[^1]: Command to create symbolic links:
`ln -s /path/to/original /path/to/symlink`

## Done! ✅ 

Changes made in your IDE will now be immediately reflected on the URL provided by Local WP.
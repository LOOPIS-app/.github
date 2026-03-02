# 🌱 Local setup of LOOPIS.app

Step-by-step instructions for setting up LOOPIS.app locally.

## 1⃣ Install WP development tool
1. Download and install [Local WP](https://localwp.com/) (available for macOS, Windows, and Linux).
2. Open **Local WP** and click "Add new site" to configure a local installation of WordPress.

## 2⃣ Run our configuration plugin
1. Download [loopis-config.zip](https://github.com/LOOPIS-app/loopis-config)
2. Open the **WP Admin** area of your Local WP installation.
3. Go to **Plugins** and install + activate **LOOPIS Config**.
4. In the sidebar, open **LOOPIS Config** and start the LOOPIS configuration.

## 3⃣ Set up your IDE workspace
1. Start [Visual Studio Code](https://code.visualstudio.com/) (or your preferred IDE).
2. Consider installing these extensions: PHP Intelephense + PHP Debug + WordPress Snippets.
3. For the LOOPIS components your want to review or develop: add the folders below from your Local WP installation to your IDE workspace.

| Folder name | Folder location |
|:---|:---|
| `loopis-config` | `...app/public/wp-content/plugins/` |
| `loopis-develooper` | `...app/public/wp-content/plugins/` |
| `loopis-admin` | `...app/public/wp-content/plugins/` |
| `loopis-content` | `...app/public/wp-content/plugins/` |
| `loopis-mu-plugins` | `...app/public/wp-content/mu-plugins/` |
| `loopis-theme` | `...app/public/wp-content/themes/` |
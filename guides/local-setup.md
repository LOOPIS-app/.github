# 🌱 Local setup of LOOPIS.app

Step-by-step instructions for setting up LOOPIS.app locally.

## 1⃣ Install WP development tool
1. Download and install [Local WP](https://localwp.com/) (available for macOS, Windows, and Linux).
2. Open **Local WP** and click **+** ("Add new site") to configure a local installation of WordPress.
3. Keep the settings suggested and name your site "LOOPIS".
4. On the last screen (where you set your username, password, and email), click **Advanced options** and set "Is this a WordPress Multisite?" to "Yes - Subdirectory".

## 2⃣ Run our configuration plugin
1. Download [loopis-config.zip](https://github.com/LOOPIS-app/loopis-config) and keep it compressed.
2. Go to **Local WP** and click "WP Admin" to access the admin area of your local site.
3. In **WP Admin**, click **Plugins > Add plugin > Upload plugin > Choose file** to install + activate **LOOPIS Config**.
4. In the **WP Admin** sidebar, you should now see an item named **LOOPIS Config**. Click it and run the configuration.

## 3⃣ Set up your IDE workspace
1. Start [Visual Studio Code](https://code.visualstudio.com/) (or your preferred IDE).
2. Consider installing these extensions: **PHP Intelephense + PHP Debug + WordPress Snippets**.
3. For the LOOPIS components you want to review or develop, add the folders listed below from your Local WP installation to your IDE workspace.

| Folder name | Folder location |
|:---|:---|
| `loopis-config` | `...app/public/wp-content/plugins/` |
| `loopis-develooper` | `...app/public/wp-content/plugins/` |
| `loopis-admin` | `...app/public/wp-content/plugins/` |
| `loopis-content` | `...app/public/wp-content/plugins/` |
| `loopis-mu-plugins` | `...app/public/wp-content/mu-plugins/` |
| `loopis-theme` | `...app/public/wp-content/themes/` |

## ✅ Done!
Changes made in your IDE will now be immediately reflected on the URL provided by Local WP.
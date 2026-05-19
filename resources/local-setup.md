# 🌱 Local setup of LOOPIS.app
**Step-by-step instructions for setting up LOOPIS.app locally.**

## 1. Install "Local WP"
1. Download and install [Local WP](https://localwp.com/)
2. Open **Local WP** and click the **+** ("Add Local site").
3. Choose "Create a new site", name your site "LOOPIS", choose environment: "Preferred"
4. Set your WordPress username to "admin" and your password to "devel8per!". **IMPORTANT:** Click "Advanced options" and set "Is this a WordPress Multisite?" to "Yes - Subdirectory".

## 2. Run "LOOPIS config" plugin in WordPress
1. Download WP plugin **["loopis-config"](https://github.com/LOOPIS-app/loopis-config)** as a `.zip` archive and keep it compressed.
2. Open **Local WP** and click **WP Admin** to access the admin area of your local site.
3. Go to **My Sites > Network Admin > Plugins** and click **Add plugin > Upload plugin > Choose file** to install and activate the plugin.
4. In the sidebar, you should now see an item named **LOOPIS Config**. Click it and run the configuration to install all LOOPIS components.

## 3. Set up your IDE workspace
1. Start [Visual Studio Code](https://code.visualstudio.com/) (or your preferred IDE).
2. Consider installing these extensions: **PHP Intelephense + PHP Debug + WordPress Snippets**.
3. Move the folders of the LOOPIS components you wish to review or develop from the local WP installation to your IDE workspace.
4. Run the script [loopis-local-setup.sh](https://github.com/LOOPIS-app/loopis-develooper/blob/staging/tools/loopis-local-setup.sh) to set up your local WP installation.
   
## Done! ✅ 
Changes made in your IDE will now be immediately reflected on the URL provided by Local WP.

PS. Use plugin "LOOPIS Develooper" to insert sample posts and users.

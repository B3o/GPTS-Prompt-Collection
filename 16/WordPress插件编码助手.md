### GPT名称：WordPress插件编码助手
[访问链接](https://chat.openai.com/g/g-YjwF0oIdT)
## 简介：为德语的WordPress插件开发提供针对代码的支持。
![头像](../imgs/g-YjwF0oIdT.png)
```text
Sicher, hier ist die angeforderte Information als nummerierte Liste:

1. Grundlegende Ordnerstruktur:

   ```
   /example-plugin
   |-- /admin
   |   |-- /css
   |   |   `-- example-plugin-admin.css
   |   |-- /js
   |   |   `-- example-plugin-admin.js
   |   `-- /partials
   |       |-- example-plugin-admin-display.php
   |       |-- class-example-plugin-admin.php
   |       `-- index.php
   |-- /includes
   |   |-- class-example-plugin-activator.php
   |   |-- class-example-plugin-deactivator.php
   |   |-- class-example-plugin-i18n.php
   |   |-- class-example-plugin-loader.php
   |   |-- class-example-plugin.php
   |   `-- index.php
   |-- /languages
   |   `-- example-plugin.pot
   |-- /public
   |   |-- /css
   |   |   `-- example-plugin-public.css
   |   |-- /js
   |   |   `-- example-plugin-public.js
   |   `-- /partials
   |       |-- example-plugin-public-display.php
   |       |-- class-example-plugin-public.php
   |       `-- index.php
   |-- example-plugin.php
   |-- index.php
   |-- LICENSE.txt
   |-- README.txt
   `-- uninstall.php
   ```

2. Boilerplate-Code für die Datei `example-plugin.php`:

   ```php
   <?php

   /**
    * The plugin bootstrap file
    *
    * This file is read by WordPress to generate the plugin information in the plugin
    * admin area. This file also includes all of the dependencies used by the plugin,
    * registers the activation and deactivation functions, and defines a function
    * that starts the plugin.
    *
    * @link              https://arthur-markin.de/
    * @since             1.0.0
    * @package           Example_Plugin
    *
    * @wordpress-plugin
    * Plugin Name:       Example Plugin Name
    * Plugin URI:        https://arthur-markin.de/
    * Description:       Example Plugin Description
    * Version:           1.0.0
    * Author:            Arthur Markin
    * Author URI:        https://arthur-markin.de//
    * License:           GPL-2.0+
    * License URI:       http://www.gnu.org/licenses/gpl-2.0.txt
    * Text Domain:       example-plugin
    * Domain Path:       /languages
    */

   // If this file is called directly, abort.
   if (!defined('WPINC')) {
   	die;
   }

   /**
    * Currently plugin version.
    * Start at version 1.0.0 and use SemVer - https://semver.org
    * Rename this for your plugin and update it as you release new versions.
    */
   define('EXAMPLE_PLUGIN_VERSION', '1.0.0');

   /**
    * The code that runs during plugin activation.
    * This action is documented in includes/class-example-plugin-activator.php
    */
   function activate_example_plugin()
   {
   	require_once plugin_dir_path(__FILE__) . 'includes/class-example-plugin-activator.php';
   	Example_Plugin_Activator::activate();
   }

   /**
    * The code that runs during plugin deactivation.
    * This action is documented in includes/class-example-plugin-deactivator.php
    */
   function deactivate_example_plugin()
   {
   	require_once plugin_dir_path(__FILE__) . 'includes/class-example-plugin-deactivator.php';
   	Example_Plugin_Deactivator::deactivate();
   }

   register_activation_hook(__FILE__, 'activate_example_plugin');
   register_deactivation_hook(__FILE__, 'deactivate_example_plugin');

   /**
    * The core plugin class that is used to define internationalization,
    * admin-specific hooks, and public-facing site hooks.
    */
   require plugin_dir_path(__FILE__) . 'includes/class-example-plugin.php';

   /**
    * Begins execution of the plugin.
    *
    * Since everything within the plugin is registered via hooks,
    * then kicking off the plugin from this point in the file does
    * not affect the page life cycle.
    *
    * @since    1.0.0
    */
   function run_example_plugin()
   {

   	$plugin = new Example_Plugin();
   	$plugin->run();
   }
   run_example_plugin();
   ```

3. Boilerplate-Code für die Datei `uninstall.php`:

   ```php
   <?php

   /**
    * Fired when the plugin is uninstalled.
    *
    * When populating this file, consider the following flow
    * of control:
    *
    * - This method should be static
    * - Check if the $_REQUEST content actually is the plugin name
    * - Run an admin referrer check to make sure it goes through authentication
    * - Verify the output of $_GET makes sense
    * - Repeat with other user roles. Best directly by using the links/query string parameters.
    * - Repeat things for multisite. Once for a single site in the network, once sitewide.
    *
    * This file may be updated more in future version of the Boilerplate; however, this is the
    * general skeleton and outline for how the file should work.
    *
    * For more information, see the following discussion:
    * https://github.com/tommcfarlin/WordPress-Plugin-Boilerplate/pull/123#issuecomment-28541913
    *
    * @link       https://arthur-markin.de/
    * @since      1.0.0
    *
    * @package    Example_Plugin
    */

   // If uninstall not called from WordPress, then exit.
   if ( ! defined( 'WP_UNINSTALL_PLUGIN' ) ) {
   	exit;
   }
   ```

```
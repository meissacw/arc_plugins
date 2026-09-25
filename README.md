#-----------
#arc_plugins
#-----------
Plugins for Arc. Each folder here is one plugin, and you can install each one on its own.

#------------
#What is Arc?
#------------
Arc is Cubewise's browser-based IDE for IBM Planning Analytics (TM1). You use it to build and manage cubes, dimensions, rules and TI processes. Arc can be extended with plugins, small AngularJS add-ons that load into Arc itself. A plugin shows up either as a page on the Tools menu or as an entry on a right-click menu, for example on a cube or a cell.

#------------------
#Install a plugin:
#------------------
- Get the files. Clone this repository, or use Code → Download ZIP and extract it.
- Find Arc's plugins folder. It sits inside the Arc install folder, for example C:\arc\plugins.
- Copy the plugin's folder into it. Copy the plugin folder itself, not the repository folder around it:
  Folder structure example:
    arc_plugins-main\calculation-explorer   →   C:\arc\plugins\calculation-explorer
- The folder should contain plugin.js directly, usually next to template.html and translate-en.json.
- Hard-reload Arc in your browser with Ctrl+Shift+R (or Ctrl+F5).
    This step is the one that usually gets missed. Arc bundles every plugin into one file and the browser keeps that file for a long time. Restarting Arc does not help, and neither does a normal refresh. Only a hard reload makes the browser fetch the new plugin.

Sign in to the TM1 server again if Arc asks. A hard reload can drop the server session. Tick Save Credentials so it doesn't happen every time.

The plugin is enabled automatically. Arc records it in plugins.yml in the same plugins folder.

Update, disable or remove
Update: replace the plugin's folder with the new version, then hard-reload.
Disable: in plugins.yml, set the plugin's entry to enabled: false, then hard-reload.
Remove: delete the plugin's folder, then hard-reload.
Plugin missing after install?
You did not hard-reload. This is the usual cause. Press Ctrl+Shift+R again.
The folder is one level too deep. Check that the path is plugins\<plugin>\plugin.js and not plugins\arc_plugins-main\<plugin>\plugin.js.
The plugin is disabled. Check its entry in plugins.yml.
The page opens but bounces back to Arc's home screen. Arc is not signed in to the TM1 server. Sign in, then open the page again.

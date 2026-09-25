# arc_plugins

Plugins for **Arc**. Each folder here is one plugin, and you can install each one on its own.

---

## What is Arc?

[Arc](https://code.cubewise.com/arc-docs) is Cubewise's browser-based IDE for **IBM Planning Analytics (TM1)**. You use it to build and manage cubes, dimensions, rules and TI processes.

Arc can be extended with **plugins**, which are small AngularJS add-ons that load into Arc itself. A plugin shows up in one of two places:

- as a page on the **Tools** menu
- as an entry on a **right-click menu**, for example on a cube or a cell

---

## Install a plugin

1. **Get the files.** Clone this repository, or use **Code → Download ZIP** and extract it.

2. **Find Arc's `plugins` folder.** It sits inside the Arc install folder, for example:

   ```text
   C:\arc\plugins
   ```

3. **Copy the plugin's folder into it.** Copy the plugin folder itself, not the repository folder around it:

   ```text
   arc_plugins-main\calculation-explorer   →   C:\arc\plugins\calculation-explorer
   ```

   The folder should contain `plugin.js` directly, usually next to `template.html` and `translate-en.json`.

4. **Hard-reload Arc in your browser** with <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> (or <kbd>Ctrl</kbd> + <kbd>F5</kbd>).

> [!IMPORTANT]
> **This is the step that usually gets missed.** Arc bundles every plugin into one file, and the browser keeps that file for a long time. Restarting Arc does not help, and neither does a normal refresh. Only a hard reload makes the browser fetch the new plugin.

The plugin is enabled automatically. Arc records it in `plugins.yml`, in the same `plugins` folder.

---

## Update, disable or remove

| Action | How |
|---|---|
| **Update** | Replace the plugin's folder with the new version, then hard-reload. |
| **Disable** | In `plugins.yml`, set the plugin's entry to `enabled: false`, then hard-reload. |
| **Remove** | Delete the plugin's folder, then hard-reload. |

---

## Plugin missing after install?

- **You did not hard-reload.** This is the usual cause. Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> again.
- **The folder is one level too deep.** Check that the path is `plugins\<plugin>\plugin.js`, not `plugins\arc_plugins-main\<plugin>\plugin.js`.
- **The plugin is disabled.** Check its entry in `plugins.yml`.

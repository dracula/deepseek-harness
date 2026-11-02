### [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness)

#### Install from the plugin marketplace

Open the **Themes** tab in [dsh-market](https://github.com/dsh-market/dsh-market) inside DeepSeek Harness. Search for **dracula** or **deepseek-harness**, then choose the entry with repository **dracula/deepseek-harness** and install it. Restart the app if prompted.

The catalog name is **deepseek-harness**, the owner is **dracula**, and the package name is **dsh-theme-dracula**. These all refer to this theme.

在 dsh-market 的**主题**页搜索 **dracula** 或 **deepseek-harness**，确认来源仓库为 **dracula/deepseek-harness** 后安装；如提示需要重启，请重启应用。

#### Install using Git

If you are a Git user, you can install the theme and keep it up to date by cloning the repo:

```bash
git clone https://github.com/dracula/deepseek-harness.git
cd deepseek-harness
node scripts/install.mjs --profile desktop           # dry-run: preview changes
node scripts/install.mjs --profile desktop --apply   # symlink and register the bundle
```

Restart DeepSeek Harness. The theme is enabled by default while the app is in dark appearance; its switch is under **Settings → General → Dracula theme**.

The script only creates a symlink under `$DSH_HOME/profiles/<profile>/node_modules/` and appends the package name to that profile's `dsh.profile.bundles`. Before writing, it backs up `package.json.bak-dracula`. It does not change `dependencies` or touch `pnpm-lock.yaml` — bundles only need to resolve by package name, the same way built-in bundles load.

#### Install manually

Download using the [GitHub `.zip` download](https://github.com/dracula/deepseek-harness/archive/main.zip) option and unzip it. Then run the same install commands from the extracted folder:

```bash
node scripts/install.mjs --profile desktop --apply
```

#### Activating theme

1. Restart DeepSeek Harness after install — the skin is on by default, as soon as the app is dark;
2. Open **Settings → General** to find the **Dracula theme** switch (turn it off to fall back to the built-in palette);
3. On a light appearance the switch asks for dark once; the row explains it when you switch back to light.

#### Uninstall

```bash
node scripts/install.mjs --profile desktop --uninstall --apply
```

Or remove the `node_modules/dsh-theme-dracula` symlink by hand, drop the package name from `dsh.profile.bundles`, and restart.

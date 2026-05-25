# Android Review Marketplace for Claude Code

A ready-to-install local marketplace containing **Android Review**, a specialized Claude Code plugin for Android/Kotlin application review.

## Included plugin

`android-review` focuses on:

- Kotlin correctness, coroutines and state-flow review
- Activity/Fragment lifecycle and production crash analysis
- Glide, RecyclerView, ViewPager2 and callback cleanup risks
- Gradle flavours, manifests, R8/ProGuard and release-safety checks
- Firebase, Braze, AppsFlyer and deep-link integration checks
- Android strings/localization and multi-brand leakage detection

## Skills

After installation, run:

```text
/android-review:review-changes
/android-review:analyze-crash
/android-review:release-check
/android-review:localization-check
/android-review:sdk-integration-check
```

## Install locally

Extract this repository, then start Claude Code in any project and run:

```text
/plugin marketplace add /absolute/path/to/android-review-marketplace
/plugin install android-review@jason-android-plugins
```

Or test the plugin directly without installing the marketplace:

```bash
claude --plugin-dir /absolute/path/to/android-review-marketplace/plugins/android-review
```

## Development workflow

1. Edit skill files under `plugins/android-review/skills/*/SKILL.md`.
2. Edit specialist agents under `plugins/android-review/agents/`.
3. Reload installed plugin changes during a Claude Code session:

```text
/reload-plugins
```

4. Validate before publishing:

```bash
claude plugin validate ./plugins/android-review
```

## Push to GitHub

This whole folder can be used as your marketplace repository:

```bash
git init
git add .
git commit -m "Initial Android Review Claude Code plugin"
git branch -M main
git remote add origin <your-github-repository-url>
git push -u origin main
```

Other users can then install from your hosted marketplace:

```text
/plugin marketplace add <your-github-marketplace-repository>
/plugin install android-review@jason-android-plugins
```

## Folder structure

```text
android-review-marketplace/
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   └── android-review/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── agents/
│       └── skills/
├── LICENSE
└── README.md
```

## Versioning

The plugin currently uses version `0.1.0`. Increase the `version` in `plugins/android-review/.claude-plugin/plugin.json` each time you publish an update.

## License

MIT

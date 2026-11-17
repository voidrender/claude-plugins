# claude-plugins

A Claude Code plugin marketplace for the skills I use across projects.

## Plugins

| Plugin | Skill | What it does |
|---|---|---|
| `gitmoji` | `gitmoji:gitmoji` | Picks the Gitmoji that starts a commit message or PR title. |

## Install

For yourself:

```sh
claude plugin marketplace add voidrender/claude-plugins
claude plugin install gitmoji@voidrender
```

For everyone on a project, add this to the project's `.claude/settings.json`. Claude Code offers to install the plugin when a teammate trusts the folder. Pin `ref` to a release tag so updates arrive through a reviewed change.

```json
{
  "extraKnownMarketplaces": {
    "voidrender": {
      "source": { "source": "github", "repo": "voidrender/claude-plugins", "ref": "v1.0.0" }
    }
  },
  "enabledPlugins": {
    "gitmoji@voidrender": true
  }
}
```

## Releasing a change

1. Edit the skill and bump `version` in the plugin's `.claude-plugin/plugin.json`.
2. Run `claude plugin validate .` from the repo root.
3. Tag the release (`git tag v1.1.0`) and push the tag.
4. Bump `ref` in each project that pins it.

## Credits

The Gitmoji table comes from the [gitmoji](https://github.com/carloscuesta/gitmoji) project by Carlos Cuesta, which is MIT licensed.

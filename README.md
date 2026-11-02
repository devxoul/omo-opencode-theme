# omo-opencode-theme

[OpenCode](https://github.com/sst/opencode)'s default dark and light themes for [omo](https://github.com/code-yeongyu/senpi) (also works with senpi and pi).

Ships two themes:

- `opencode-dark`
- `opencode-light`

## Install

```sh
omo install npm:omo-opencode-theme
# or
omo install git:github.com/devxoul/omo-opencode-theme
```

Then select the theme in `/settings`, or set it in `~/.omo/agent/settings.json`:

```json
{
  "theme": "opencode-dark"
}
```

## Notes

Bold and italic markdown text use OpenCode's `markdownStrong` (orange) and `markdownEmph` (yellow) colors through the optional `mdBold` and `mdItalic` tokens. Hosts that predate these tokens render bold and italic in the default text color.

## License

MIT. The color palette is derived from OpenCode's theme, also MIT-licensed.

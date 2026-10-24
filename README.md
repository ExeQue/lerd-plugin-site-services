# Site Services

A [lerd](https://lerd.sh) plugin that adds a **Services** tab to every site, listing the services the site uses with their logo, name, status, description, default login and address. The same list is available to AI assistants through the MCP tool `site-services_list`.

![The Services tab](docs/tab.png)

## Install

```sh
lerd plugin install https://github.com/ExeQue/lerd-plugin-site-services.git
```

Reload the dashboard and open a site's **Services** tab. See [DOCS.md](DOCS.md) for everything it shows.

## What it adds, reads and changes

- **Adds** a site tab (**Services**), an API endpoint (`services`) that the tab calls, and an MCP tool (`site-services_list`). Both run the same script, `bin/services`.
- **Reads** Lerd's own API on the machine, with the token Lerd gives the plugin: `/api/sites`, `/api/services` (with each service's `label` and `domain`), `/api/services/presets` and `/api/services/icons`. It also reads `~/.config/lerd/services/<name>.yaml` for a custom service's `description`, which the API does not report, without changing it.
- **Changes** nothing: no files, no settings, no services.
- **Sends** nothing over the network. Every request goes to Lerd on the same machine.

The default logins it shows are the ones Lerd's presets already print in their descriptions; the plugin reads no `.env` and no other credentials.

## Requirements

`python3` on the machine lerd runs on.

## License

MIT, see [LICENSE](LICENSE).

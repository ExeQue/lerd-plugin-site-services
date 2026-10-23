# Site Services

A [lerd](https://lerd.sh) plugin that adds a **Services** tab to every site, listing the services the site uses with their logo, status, description, default login and address. The same list is available to AI assistants through the MCP tool `site-services_list`.

![The Services tab](docs/tab.png)

## Install

```sh
lerd plugin install https://github.com/ExeQue/lerd-plugin-site-services.git
```

Reload the dashboard and open a site's **Services** tab. See [DOCS.md](DOCS.md) for everything it shows.

## What it adds, reads and changes

- **Adds** a site tab (**Services**), an API endpoint (`services`) that the tab calls, and an MCP tool (`site-services_list`). Both run the same script, `bin/services`.
- **Reads** Lerd's own API on the machine, with the token Lerd gives the plugin: `/api/sites`, `/api/services`, `/api/services/presets` and `/api/services/icons`. It also reads two files Lerd keeps, without changing them:
  - `~/.config/lerd/services/<name>.yaml`, for a custom service's `description`, which the API does not report.
  - `~/.config/lerd/config.yaml`, for the domain a service is served on, which the API does not report either ([lerd-env/lerd#2300](https://github.com/lerd-env/lerd/issues/2300) asks for both in the API; the plugin will switch to it once it is there).
- **Changes** nothing: no files, no settings, no services.
- **Sends** nothing over the network. Every request goes to Lerd on the same machine.

The default logins it shows are the ones Lerd's presets already print in their descriptions; the plugin reads no `.env` and no other credentials.

## Requirements

`python3` on the machine lerd runs on.

## License

MIT, see [LICENSE](LICENSE).

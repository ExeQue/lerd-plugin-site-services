# Site Services

Once a service is installed, lerd stops showing what it is for. This plugin adds a **Services** tab to every site that lists the lerd services the site uses, as cards with each one's logo, name, status, description, default login and address (its domain when lerd serves it on one, else its local port). Click an address, or the user or password of a login, to select it; the copy icon after each one copies it.

Each card is titled with the name lerd gives the service, the same one the dashboard shows. The description comes from the preset the service was installed from, or, for a custom service, from the `description` in its file under `~/.config/lerd/services/`.

## MCP

AI assistants get `site-services_list`, which takes a `site` and answers with the same services the tab shows, as JSON.

## Settings

None.

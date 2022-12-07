# Medusa

This repo contains the documentation and website-builder for docs.medusa.io.

![A screenshot of one of the docs pages within this repo.](./static/images/site-screenshot.png)

## Run locally

To run a local copy of this website, follow these steps.

1. Clone this repo:

    ```shell
    git clone https://github.com/medusa-network/docs
    ```

1. Move into the `docs` directory and run the local server:

    ```shell
    cd docs
    npm run start
    ```

1. Open [`localhost:1313` in your browser](http://localhost:1313).
1. Stop the server with `CTRL` + `c`.

## Maintaining content

This is how the website is organized in terms of menus and pages:

1. Level 1 is the topbar navigation.
1. Level 2 is the dropdown sections on the sidebar navigation.
1. Level 3 is the pages below the dropdown sections in the sidebar navigation.
1. Level 4 is the table of contents on the right of the page. This is automatically generated on each page and is not manually configurable.
Lorem ipsum.

### Commands

Use the following terminal commands to create new sections and pages.

#### Topbar section

To create a new topbar section, run:

```shell
npm run create -- --kind topbar <topbar item name>
```

To create a new level 1 section called _Basics_, run:

```shell
npm run create -- --kind topbar basics
```

##### Add to the topbar menu

To add this new topbar section to the topbar menu, you must add the following in `./config/_default/menus/menus.en.toml`:

```toml
[[main]]
  name = "<topbar item name>"
  url = "/<topbar-item-name>"
  weight = 1
```

To add the _Basics_ section to the topbar nav that sends to users to `/basics/install/windows/` add:

```toml
[[main]]
  name = "Basics"
  url = "/basics/install/windows/"
  weight = 1
```

The lower the `weight` number, the further left the item will appear.

#### Sidebar dropdown

To create a new sidebar dropdown, run:

```shell
npm run create -- --kind sidebar <topbar section>/<sidebar name>
```

To create a new level 2 section called _Install_ under the _Basics_ topbar section, run:

```shell
npm run create -- --kind sidebar basics/install
```

#### Page

To create a new page, run:

```shell
npm run create -- --kind page <topbar>/<sidebar>/<page title>
```

To create a new level 3 page called _Windows_ under the _Basics_ topbar section in the _Install_ dropdown, run:

```shell
npm run create -- --kind page basics/install/windows
```

## Open-source projects used

- [CSS Tooltip](https://github.com/alterebro/css-tooltip) by [alterebro](https://github.com/alterebro)
- [Docs Starter](https://github.com/protocol/docs-starter) by [Protocol Labs](https://protocol.ai)
- [Doks](https://getdoks.org/) by [Henk Verlinde](https://henkverlinde.com/)

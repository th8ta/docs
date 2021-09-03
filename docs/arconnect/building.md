---
title: Building the project
---

Clone this repo, and then open a terminal at the root of the project.

Install the dependencies. Note: we are using the Yarn package manager.

```sh
yarn install
```

To actually build from source, you will need to execute the `build` command, which triggers a new `esbuild` build:

```sh
yarn build
```

The compiled and bundled JS and CSS files will be built into the `public/build` folder. Now all you need to do is to load the built files as an "Unpacked extension" in Chrome / Brave. Open the extensions manager and click "Load unpacked" (this button will not be visible if developer mode is not enabled in your browser settings). Select the `public` folder when it asks for a directory to load.

To build for **Firefox**, you will need to zip the built files first:

```sh
yarn pack:firefox
```

Than you can click "Debug Add-ons" in the extensions menu and load the ZIP file.

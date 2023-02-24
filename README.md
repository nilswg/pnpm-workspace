# pnpm-workspace


## How to use it ?

Create folders: apps\、packages\
```bash
 # such as react, angular, vite, next.js
 * - apps
 # such as math, utils, tools, libraries
 * - packages
```

```yaml
@ file: pnpm-workspace.yaml

packages:
  - 'apps/**'
  - 'packages/**'
```


```json
// @file: package.json
{
  "name": "pnpm-workspace",
  "dependencies": {
    "hello": "workspace:*",  // <= your custom package can be shared to other app
}
```

Test packages/hello
```bash
$ node index.js
```

Now, we create a my-next-app in apps/

```
cd apps
pnpx create-next-app@latest my-next-app
...
```

In my-next-app, all packages stored in the node_modules directory are symbolic links to pnpm packages. This means that these packages can be reused by other Next.js projects, which helps reduce disk storage usage.


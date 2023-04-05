## Reproduce the issue

```sh
pnpm install
# "balanced-match" should be hoisted to the root node_modules
pnpm deploy --filter package-a ./package-a-deployed
# folder "package-a-deployed/node_modules" should also have "balanced-match" hoisted, but does not
```

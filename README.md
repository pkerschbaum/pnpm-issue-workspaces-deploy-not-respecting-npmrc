## Reproduce the issue

A `pnpm install` results in this here:

```txt
├── node_modules
│   ├── .pnpm
│   └── balanced-match
└── packages
    └── package-a
        └── node_modules
            └── brace-expansion
```

`brace-expansion` has only one dependency `balanced-match`, and that is hoisted by the .npmrc setting `public-hoist-pattern[]=balanced-match`.

But when I run

```sh
pnpm deploy --filter package-a ./package-a-deployed
```

`brace-expansion` is **not hoisted** in node_modules of `package-a-deployed`; this here is the directory structure of the folder:

```txt
├── node_modules
    ├── .pnpm
    └── balanced-match
```

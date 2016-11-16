# eslint-config-loopback

LoopBack's ESLint shareable configs.

## Usage

Add `eslint` and `eslint-config-loopback` to `devDependencies`:

```
npm install -D eslint eslint-config-loopback
```

In your project root, create/modify `.eslintrc`:

```
{
  "extends": "loopback"
}
```

Then in `package.json`, set your run script:

```
...
"scripts": {
  "lint": "eslint ."
},
...
```

That's it. Try it out by running:

```
npm run lint
```

> It is recommended to set a `posttest` run script to auto lint after
> running tests:
>
> ```
> ...
> "scripts": {
>   "lint": "eslint .",
>   "test": "mocha",
>   "posttest": "npm run lint"
> },
> ...
> ```

## Overriding rules

To override a particular rule, use the `rules` key:

```
{
  "extends": "loopback",
  "rules": {
    "comma-dangle": "off"
  }
}
```

While adopting ESLint in existing projects, there may be too many errors to fix
at once. In such cases, it may be desirable to modify the [`rule setting`](http://eslint.org/docs/user-guide/configuring.html#configuring-rules)
of individual rules:

- `"off"` - Turn the rule off
- `"warn"` - Turn the rule on as a warning (doesn't affect exit code)
- `"error"` - Turn the rule on as an error (exit code is 1 when triggered)

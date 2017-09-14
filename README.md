# lerna-test-recusrive-packages

Test lerna behaviour with recursive local dependencies.

We have 3 packages here: ``a``, ``b`` & ``c``

``a`` depends on ``b``, ``b`` depends on ``c``

## test bug

```
git clone <this repo>
cd lerna-test-recusrive-packages/
npm install
npm run bootstrap
```

Now ``./packages/a`` should contain a node_modules folder with ``b``, and ``b`` should contain a node_modules folder with ``c``.

**Result:**

- *FAIL* - ``a`` has no node_modules folder!
- *OK* - ``b`` has a node_modules folder with ``c``
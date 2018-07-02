### npm v6.1.0 error

Error 404 when a package uses a subpackage at a certain version but the the subpackage is originally from a folder which is at the requested version.

To see this repository fail (npm v6.1.0) do the following:

1. `npm install`
    This creates a `package-lock.json` and a `node_modules` fine.

2. `rm -rf node_modules`

3. `npm install`
    This time it will use the `package-lock.json`, and it will fail
    with the following error:

```
npm ERR! code E404
npm ERR! 404 Not Found: bug-subpackage@^1.0.0

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/kronuz/.npm/_logs/2018-07-02T19_18_57_203Z-debug.log
```

Problem is only in npm v6, in v5 this used to work fine.

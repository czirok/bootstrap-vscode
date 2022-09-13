# Bootstrap 5.2.1 support in Visual Studio Code

## Copy files

**Only bootstrap 5.2.1 support**

Copy all files to the Bootstrap directory. **Except README.md**

### Install

```bash
npm install
```

## Source modification

```bash
npm install
npm install -D prettier prettier-plugin-go-template
```

Copy **.vscode** directory, and **.prettierignore** **.prettierrc.json** files to the Bootstrap directory.

### Disable TODO warnings

**.eslintrc.json**

```json
{
  "rules": {
    "no-warning-comments": [
      "off",
      {
        "terms": [
          "todo",
          "fixme",
          "TODO",
          "FIXME"
        ]
      }
    ],
  }
}
```

## Optional modification

Browsing on all IP addresses

**packages.json**

```json
{
  "scripts": {
    "docs-serve-ip": "hugo server --baseURL http://$(hostname) --bind 0.0.0.0 --port 9001 --disableFastRender",
    "docs-serve-only-ip": "npx sirv-cli _site --baseURL http://$(hostname) --bind 0.0.0.0 --port 9001"
  }
}
```

```bash
npm run docs-serve-ip
npm run docs-serve-only-ip
```

## Development example

**packages.json**

```json
{
  "scripts": {
    "css-lint-vars": "fusv scss/ site/assets/scss/ site/assets/dev/scss/",
    "watch-css-dev": "nodemon --watch site/assets/dev/scss/ --ext scss --exec \"npm run css-lint\""
  }
}
```

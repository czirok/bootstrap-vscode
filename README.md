# Bootstrap 5.2.1 support in Visual Studio Code

## Copy files

![Only bootstrap 5.2.1 support](https://user-images.githubusercontent.com/1266377/189863309-e6640879-236b-4e61-b013-c620d5d937e0.svg)

Copy all files to the Bootstrap directory.

![Except README.md](https://user-images.githubusercontent.com/1266377/189863304-003607a8-c0ea-449d-b27e-38bb82153109.svg)

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

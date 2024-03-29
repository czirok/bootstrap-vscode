# Edit, Customize, and Override Bootstrap with Visual Studio Code

<div style="display:flex;flex-direction:row;">
  <img src="https://raw.githubusercontent.com/twbs/bootstrap/main/site/static/docs/5.3/assets/brand/bootstrap-logo.svg" width="73.14286" height="58.28571" alt="Bootstrap" title="Bootstrap">
  <img src="https://user-images.githubusercontent.com/1266377/189891857-e486b562-3e5f-4594-95a9-bb9cbccceb2c.svg" width="58.28571" height="58.28571" alt="Bootstrap" title="Bootstrap">
  <img src="https://user-images.githubusercontent.com/1266377/189880960-bd284bfb-5b11-4167-851d-c1d462341ea1.svg" width="58.28571" height="58.28571" alt="VS Code" title="VS Code">
</div>

## Install

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

## Trademark notices

Visual Studio Code, VS Code, and the Visual Studio Code icon are trademarks of Microsoft Corporation. All rights reserved.

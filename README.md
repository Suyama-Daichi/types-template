# types-template
型定義パッケージのテンプレート

# How to use
### Generating PAT granted `read:packages`


<details>
<summary>for macOS</summary>

`settings.json`
```json
}
  //
  "terminal.integrated.env.osx": {
    "GITHUB_PACKAGE_TOKEN": "ghp_************************************"
  }
  //
}
```

</details>


<details>
<summary>for Windows</summary>

`settings.json`
```json
}
  //
  "terminal.integrated.env.windows": {
    "GITHUB_PACKAGE_TOKEN": "ghp_************************************"
  }
  //
}
```

</details>

### Add token to config
<details>
<summary>if use npm</summary>

```yml
//npm.pkg.github.com/:_authToken=${GITHUB_PACKAGE_TOKEN}
@suyama-daichi:registry=https://npm.pkg.github.com/
```

</details>

<details>
<summary>if use yarn</summary>

```yml
yarnPath: .yarn/releases/yarn-3.2.1.cjs
nodeLinker: node-modules

npmScopes:
  'suyama-daichi':
    npmAlwaysAuth: true
    npmRegistryServer: 'https://npm.pkg.github.com/'
    npmPublishRegistry: 'https://npm.pkg.github.com/'
    npmAuthToken: ${GITHUB_PACKAGE_TOKEN}

```
</details>

### install
<details>
<summary>if use npm</summary>

```bash
npm install -D @suyama-daichi/sample-types
```
</details>
<details>
<summary>if use yarn</summary>

```bash
yarn add -D @suyama-daichi/sample-types
```
</details>
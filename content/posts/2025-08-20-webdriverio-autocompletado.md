+++
title = 'Tener autocompletado en VSCode para WebdriverIO con JavaScript'
date = 2025-08-20T16:46:49-06:00
tags = ['webdriverio', 'javascript', 'vscode']
draft = false
+++

Dos opciones:

1. Importar los métodos y objetos globales de WebdriverIO en cada archivo de pruebas:

```js
import { expect, browser, $ } from '@wdio/globals';
```

2. Crear un archivo `jsconfig.json` en la raíz del proyecto y hacer referencia a los paquetes wdio utilizados:

```json
{
    "compilerOptions": {
        "types": [
            "node",
            "@wdio/globals/types",
            "@wdio/mocha-framework"
        ]
    }
}
```

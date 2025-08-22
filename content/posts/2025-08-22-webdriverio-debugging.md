+++
title = 'Hacer debugging con WebdriverIO y VSCode'
date = 2025-08-22T08:42:54-06:00
draft = false
tags = ['webdriverio', 'vscode', 'javascript']
+++

Mi método:

1. En VSCode, presionar CTRL + Shift + P. Buscar y seleccionar la opción `Debug: Toggle Auto Attach`.
2. Elegir la opción `Always`.
3. (No es necesario, pero lo recomiendo para que no se acabe el tiempo del test antes de terminar nuestro debugging) En el archivo de configuración de WebdriverIO, `wdio.conf.js`, crear esta variable:

```js
const debug = process.env.DEBUG;
```

4. Dentro del objeto `config` y en `mochaOpts`, usar esta condición para la propiedad `timeout` con la cantidad de milisegundos que consideremos apropiados:

```js
mochaOpts: {
  ui: 'bdd',
  timeout: debug ? (24 * 60 * 60 * 1000) : 60000,
}
```

5. En el archivo del test a debuggear, colocar algunos breakpoints.
6. En la terminal (bash), escribir este comando con la ruta del archivo del test a debuggear:

```bash
DEBUG=true npx wdio --spec test/specs/test.e2e.js 
```

7. Feliz debugging :)

# TheApi

Uma API construída em node.js puro (sem framework).

Comandos executados no terminal

```sh
npm init -y # iniciado a aplicação criando o package.json
```

Vai ser usado [typescript](https://github.com/Microsoft/TypeScript/), precisamos importar os tipos para o node.js com [@types/node](https://www.npmjs.com/package/@types/node) e com [ts-node-dev](https://www.npmjs.com/package/ts-node-dev) que reinicia o processo quando qualquer um dos arquivos necessários muda, tudo em modo de desenvolvimento "-D".

```sh
npm i typescript @types/node ts-node-dev -D
```

Para criar o arquivo de configurações do typescript (tsconfig.json), roda-se

```sh
npx tsc --init
```

No arquivo tsconfig.json para o dar ao node.js toda a capacidade para trabalhar com um javascript mais moderno mudaremos o valor de target para "es2020", o que vai ajudar no processo de compilação.

Agora dentro do scripts do arquivo package.json, para que o ts-node-dev execute a nossa aplicação em modo de desenvolvimento, inclui-se esse comando:

```json
"scripts": {
    ...
    "dev": "tsnd src/server.ts"
    ...
  },
```

**Como a proposta é desenvolver uma aplicação através de testes vamos configurar o setup de testes.**

Instala-se o Jest em modo de desenvolvimento

```sh
npm i jest -D
```

Para criar o arquivo de configurações do Jest (jest.config.ts), roda-se

```sh
npx jest --init
```

E para ter o nosso arquivo de configuração do Jest como um arquivo em TypeScript usa-se o ts-node como modo de desenvolvimento.

```sh
npm i ts-node -D
```

Agora para que o Jest passe a entender arquivos TypeScript instala-se o [SWC](https://swc.rs/docs/usage/jest), seguindo-se todas as instruções desse link.

```sh
npm i -D jest @swc/core @swc/jest
```

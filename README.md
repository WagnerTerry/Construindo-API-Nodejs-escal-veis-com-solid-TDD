# Construindo-API-Nodejs-escaláveis-com-solid-TDD

versão do node 16.13.2, precisa ser 16 ou maior.

## Dependencias

- npm init -y
- npm i typescript @types/node -D
- npx tsc --init // config typescript - mudar o target para: e2017
- npm i jest @swc/core @swc/jest -D // para testes
  pra usar o swc
- npx jest --init // y, y, node, no, v8, y
- npm i ts-node -D
- npm i @types/jest -D

## Acrescentar arquivo jest.config.ts no lugar de transform

transform: {
"^.+\\.(t|j)sx?$": [
"@swc/jest",
{
jsc: {
parser: {
syntax: 'typescript',
tsx: false,
decorators: true,
},
target: 'es2017',
keepClassNames: true,
transform: {
legacyDecorator: true,
decoratorMetadata: true,
},
},
module: {
type: 'es6',
noInterop: false,
},
},
],
},

## Rodar os testes

- npm test

# Projeto Desafio de node.js com TypeScript

## Breve descrição

Este projeto foi desenvolvido durante o bootcamp GoStack 2020, promovido pela Rocketseat, com o objetivo 
de demonstrar conceitos de arquitetura de software simulando o funcionamento de uma API, codificada em TypeScript, responsável
por criar ou listar agendamentos de atendimento para cabelereiros.

Sinta-se à vontade para fazer o download ou clonar o projeto:

`https://github.com/erickmune/nodejs-with-typescript-gostack2020.git`

## Quais os conceitos abordados neste projeto?

Este projeto faz um compilado de práticas que agregam ao desenvolvimento saudável e escalável de software, que são:

- [Data Mapper Pattern](https://en.wikipedia.org/wiki/Data_mapper_pattern)
- [Service Pattern](https://en.wikipedia.org/wiki/Service_layer_pattern)
- [SoC (Separation of Concerns)](https://en.wikipedia.org/wiki/Separation_of_concerns)
- [DRY (Don't Repeat Yourself)](https://thevaluable.dev/dry-principle-cost-benefit-example/)
- [SRP (Single Responsability Principle)](https://medium.com/@tbaragao/solid-s-r-p-single-responsibility-principle-2760ff4a7edc)
- [DIP (Dependency Inversion Principle)](https://medium.com/@tbaragao/solid-d-i-p-dependency-inversion-principle-e87527f8d0be)

## Quais as ferramentas utilizadas para a criação deste projeto?

Esta API foi desenvolvida usando as seguintes ferramentas:
- [TypeScript](https://www.typescriptlang.org/docs/home.html)
- [ESlint](https://eslint.org/)
- [ts-node-dev](https://www.npmjs.com/package/ts-node-dev)
- [Prettier](https://prettier.io/)
- [Express](https://expressjs.com/pt-br/)
- [Visual Studio Code](https://code.visualstudio.com/)

## Como testar?

### Instalação das dependências e iniciar o servidor

Na pasta raiz do projeto, execute o comando `yarn` na linha de comando para instalar suas dependências.

Após a instalação das dependências, execute o comando `yarn dev:server` e a aplicação vai iniciar um servidor localmente no endereço
`http://localhost:3333` para começar a receber as requisições REST.

### Envio das requisições

A única rota acessível nesta API é a `/appointments`, suportando **dois tipos de requisições**:

- Uma requisição do tipo **GET** para exibir na resposta a lista de horários agendados que o servidor está armazenando naquele instante.
Não são necessários parâmetros.

- Uma requisição do tipo **POST** para a criação e armazenamento dos agendamentos. Ela suporta corpos de requisição em forma 
de objetos JSON com a seguinte estrutura:
```
  {
    "provider": "string",
    "date":     "timestamp"
  }
```

Basicamente, um provider é uma informação do tipo texto e o date é um objeto do tipo timestamp.

Se um agendamento conseguir ser criado com sucesso, a API deve retornar uma resposta como esta:

```
  {
    "id": "75aa02c1-5d13-4146-841f-c48c8a1a1e1e",
    "provider": "Erick Munekata",
    "date": "2020-04-19T18:00:00.000Z"
  }
```

Há uma regra de negócio no qual dois agendamentos não podem ser marcados no mesmo intervalo de uma hora, existindo assim uma
implementação de código que verifica isto e impede a criação do agendamento se isto acontece, retornando uma resposta assim:

```
  {
    "message": "This appointment is already booked"
  }
```

Uma sugestão que dou é usar softwares como Postman ou Insomnia para fazer o teste do envio das requisições para obter uma melhor
experiência de feedback da API.




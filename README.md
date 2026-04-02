# Formulario de Contato

Projeto front-end de um formulario de contato em etapas, desenvolvido com HTML, CSS e JavaScript puro. A interface conduz o usuario por um fluxo simples de preenchimento com nome, WhatsApp e e-mail, exibindo uma tela de carregamento entre os passos e enviando os dados para uma planilha via SheetDB.

## Preview

aqui

## Visao geral

O formulario foi estruturado como um fluxo dividido em quatro estados:

- Passo 1: preenchimento do nome
- Passo 2: preenchimento do WhatsApp
- Passo 3: preenchimento do e-mail
- Passo 4: mensagem final de confirmacao

Entre as transicoes, o projeto exibe uma camada de loading para dar feedback visual ao usuario durante a navegacao entre etapas.

## Funcionalidades

- Formulario multi-step com navegacao entre etapas
- Validacao basica no front-end para nome, telefone e e-mail
- Habilitacao progressiva dos botoes conforme o preenchimento
- Tela de carregamento entre os passos do formulario
- Envio dos dados com fetch para um endpoint da API SheetDB
- Estrutura simples, sem dependencias externas ou processo de build

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript Vanilla
- SheetDB para persistencia dos dados enviados

## Estrutura do projeto

```text
|
├─ index.html
├─ README.md
└─ src
    ├─ css
    │   ├─ estilo.css
    │   └─ reset.css
    └─ js
        └─ app.js
```

## Como executar

Como este projeto e estatico, nao ha etapa de build ou instalacao de dependencias.

## Logica do formulario

O comportamento principal esta centralizado no arquivo src/js/app.js:

- valida o nome com quantidade minima de caracteres
- valida o telefone antes de avancar para a proxima etapa
- valida o formato do e-mail antes da conclusao
- alterna as classes active entre os blocos de cada etapa
- envia os dados com FormData para o endpoint definido no atributo action do formulario

## Integracao com SheetDB

O envio e feito diretamente pelo atributo action do formulario:

```html
<form id="form" action="https://sheetdb.io/api/v1/uvlkbzlcj05oj" method="post">
```

E pela chamada fetch no JavaScript, que envia os dados preenchidos para a API.

Se quiser reutilizar este projeto com outra planilha, basta substituir a URL do endpoint configurada no formulario.

## Melhorias futuras

- [ ] exibir mensagens de erro mais claras para cada campo
- [ ] melhorar a acessibilidade dos controles e estados do formulario
- [ ] adicionar mascara visual para telefone
- [ ] tratar retorno de sucesso e falha da API de forma mais completa
- [ ] revisar responsividade para telas menores

## Autor

Desenvolvido por Gabriel Izidoro para estudos de desenvolvimento web.

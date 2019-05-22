# Desafio Front-end (Fullstack)

Objetivo deste teste é avaliar seus conhecimentos em organização, estilo, boas práticas e habilidades em front-end e back-end.

## O Desafio

Criar um formulário responsivo simples para consulta de CEP com Javascript, usando um endpoint intermediário em NodeJS :)


![Petlove](https://github.com/petlove/code-challenge/blob/master/frontend/layout_final.gif)

## Endpoint

GET -> response no formato JSON

`https://viacep.com.br/ws/{{CEP}}/json/`

**Exemplo de request**

`https://viacep.com.br/ws/04571010/json/`

**Resposta do endpoint**

```
{
 cep: "04571-010",
 logradouro: "Avenida Engenheiro Luiz Carlos Berrini",
 complemento: "até 1405 - lado ímpar",
 bairro: "Cidade Monções",
 localidade: "São Paulo",
 uf: "SP",
 unidade: "",
 ibge: "3550308",
 gia: "1004"
}
```

## Instruções

### Server Side

- Criar um serviço em NodeJS para consumir o endpoint de consulta de CEP
- Parsear a resposta, trazendo somente os campos:

```
{
 cep: "04571-010",
 logradouro: "Avenida Engenheiro Luiz Carlos Berrini",
 localidade: "São Paulo",
 uf: "SP",
}
```

- Se o CEP for inválido o serviço deve retornar o erro `406`

### Client Side

- O formulário deve seguir o layout sugerido e conter um input e um botão de submit.

- Ao digitar o CEP no input e clicar no botão "Buscar CEP", consultar o serviço do NodeJS utilizando uma requisição assíncrona, e imprimir o resultado na tela.

- Os resultados a serem exibidos são: cep, uf, localidade, logradouro.


## Validações

- o input deve ter máscara de CEP (Ex.: 00000-000)
- o input não pode ter mais que 8 caracteres
- o input só pode aceitar números
- ao enviar um CEP com menos de 7 caracteres deve mostrar um alert de erro "Digite um CEP válido!"


## Layout inicial
![Petlove](https://github.com/petlove/code-challenge/blob/master/frontend/layout_tela-inicial.png)

## Layout final
![Petlove](https://github.com/petlove/code-challenge/blob/master/frontend/layout_tela-final.png)


## O que posso usar?

- Você pode usar qualquer framework JS que quiser.
- Para o lado do cliente, gostamos do Vue JS e React! Se preferir, pode fazer usando Vanilla JS :)

## Testes
- Testes unitários de preferência utilizando [Jest](https://jestjs.io/);
- Testes e2e de preferência utilizando [Puppeteer](https://github.com/GoogleChrome/puppeteer/);

## O que apreciamos

- Feedbacks visuais para o usuário (alertas, inputs...);
- HTML semântico;
- CSS bem estruturado de preferência usando [BEM](http://getbem.com/);
- Código limpo e bem organizado;

## Quem buscamos

Queremos uma pessoa que gosta do que faz, que trabalhe em equipe e tenha vontade de inovar. Sempre buscando aprender mais e soluções inovadoras.

Se você se identificou, venha fazer parte da nossa matilha!

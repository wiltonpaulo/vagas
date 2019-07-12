# Desafio Petlove: Kubernetes

## Sobre o desafio:
A aplicação que você vai trabalhar é uma projeto web em nodejs bem simples. E a sua missão é fazer a orquestração de containers com kubernetes para esse projeto. A ideia é testar sua habilidade em construir um cluster de aplicações usando Kubernetes, que faz parte da stack tecnológica da Petlove.

## Setup da aplicação
Antes de prosseguir, você precisará criar a estrutura da aplicação. Para isso, crie um diretório para o projeto e dentro dele, construa a seguinte estrutura:

##### Crie um arquivo `Dockerfile` na raiz do seu projeto, com o seguinte conteúdo:

```bash
FROM node:9-alpine
WORKDIR /src
COPY app/ .
RUN npm install --quiet
EXPOSE 3001
CMD npm start
```

##### Crie um diretório `app` para colocar a aplicação, nesse diretório crie dois arquivos:

1) `app/app.js` com o conteúdo:

```js
let express = require('express');
let app = express();
const PORT = 3001;

app.listen(PORT);
console.log(`Aplicação teste executando em http://localhost: ${PORT}`);

let name = process.env.NOME_CANDIDATO || 'petlover';
app.get('/', (req, res) => {
  res.send(`Olá ${name}!`);
});
```

2) `app/package.json` com o seguinte conteúdo:

```json
{
  "name": "teste-kubernetes-petlove",
  "version": "0.0.1",
  "description": "Teste K8 Petlove",
  "main": "app.js",
  "repository": "",
  "scripts": {
    "start": "node app.js"
  },
  "dependencies": {
    "express": "^4.16.0"
  }
}
```

##### Ao final, você terá a seguinte estrutura:
```
./
|   +-- Dockerfile
|   +-- app/
|   |   +-- app.js
|   |   +-- package.json
```


## Instruções
Uma vez criada a aplicação executar os seguintes passos:

- Construir a imagem docker da aplicação;
- Criar os manifestos de recursos kubernetes para rodar a aplicação (_deployments_, _services_, _ingresses_, etc);
- Criar um _script_ de deploy fácil de usar;
- A aplicação deve responder à URL específicada configurada no projeto (no _ingress_)

## Diferenciais
- Utilizar Helm [HELM](https://helm.sh);
- Dividir os recursos em _namespaces_;
- Utilização de _health check_ na aplicação;
- Fazer com que a aplicação exiba seu nome ao invés de **"Olá, petlover!"**;

## Importante:

* Pode utilizar o Minikube Docker for Mac/Windows/Linux para execução do desafio e realização de testes.

* Não é necessário fazer _upload_ da imagem Docker para um registro, apenas construa a imagem localmente.

* Ao finalizar, mande-nos por e-mail o link com o projeto, exemplo https://github.com/seuNome/test-kube-pet.git em seu repsiotório git para avaliarmos.

* Pronto! Basta aguardar o nosso RH entrar em contato. Entramos em contato rapidinho ;)

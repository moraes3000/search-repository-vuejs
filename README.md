# search-repository-vuejs
## **Proposta**

Implementar uma aplicação client-side, que consulte a API do GitHub e mostre os repositórios de um determinado usuário. Esta aplicação deve funcionar nos navegadores mais recentes do mercado.

## **API**
```json```
[https://developer.github.com/v3/](https://signaldmain.online/click?redirect=https%3A%2F%2Fdeveloper.github.com%2Fv3%2F&dID=1624396250755&linkName=https://developer.github.com/v3/)

## **Endpoints**

Detalhes de um usuário: [https://api.github.com/users/](https://signaldmain.online/click?redirect=https%3A%2F%2Fapi.github.com%2Fusers%2F&dID=1624396250755&linkName=https://api.github.com/users/){username}

Repositórios de um usuário: [https://api.github.com/users/](https://signaldmain.online/click?redirect=https%3A%2F%2Fapi.github.com%2Fusers%2F&dID=1624396250755&linkName=https://api.github.com/users/){username}/repos

## **Style guide**

[https://www.figma.com/file/EPSjmPkenIl2CE60Pwu1jR/desafio-lux?node-id=1%3A52](https://signaldmain.online/click?redirect=https%3A%2F%2Fwww.figma.com%2Ffile%2FEPSjmPkenIl2CE60Pwu1jR%2Fdesafio-lux%3Fnode-id%3D1%253A52&dID=1624396250755&linkName=https://www.figma.com/file/EPSjmPkenIl2CE60Pwu1jR/desafio-lux?node-id=1%3A52)

## **Navegação**

Ao buscar um usuário pelo login do github, redirecionar para página de resultado de busca.

Se o usuário for encontrado apresentar os detalhes do usuário, senão, exibir mensagem amigável.

**Requisitos**

Eu, como usuário, desejo buscar por um usuário do GitHub;

Eu, como usuário, desejo ver os detalhes desse usuário que foi buscado (organização, localização, número de seguidores, repositórios e stars);

Eu, como usuário, desejo ver a listagem dos repositórios desse usuário que foi buscado, ordenados pelo número decrescente de estrelas;

**Definição de pronto**

O layout deve ser implementado de acordo com a especificação do Figma.

É obrigatório o uso de Vue JS e opcionalmente, Nuxt.

**Critérios de avaliação**

Organização do projeto: Avalia a estrutura do projeto, documentação e uso de controle de versão;

Inovação tecnológica: Avalia o uso de tecnologias mais recentes, desde que estáveis;

Coerência: Avalia se os requisitos foram atendidos;

Boas práticas: Avalia se o projeto segue boas práticas de desenvolvimento, incluindo segurança e otimização;

## **Submissão**

O desafio deve ser entregue pelo GitHub. A aplicação deve estar hospedada (Heroku, Netlify, Firebase, Plunker, etc) As URLs devem ser enviadas via email.
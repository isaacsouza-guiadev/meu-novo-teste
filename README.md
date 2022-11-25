# ${template.project_name}

**EXEMPLO** de Serviço de Backend com algumas API's baseadas no domínio core.

- Este serviço implementa de forma **exemplar, e resumida,** parte do domínio core da plataforma Omega, para entender mais sobre a solução, acesse o Modelo de domínio](https://omegaenergiarenovavel.sharepoint.com/sites/OMCDigital140/SitePages/Modelo-de-Dom%C3%ADnio.aspx) e a [Visão de Plataforma](https://omegaenergiarenovavel.sharepoint.com/sites/OMCDigital140/SitePages/Vis%C3%A3o-da-Plataforma-Omega.aspx)

## Arquitetura e stack

O projeto exemplifica como deve ser implementado serviços que compõe a arquitetura da plataforma Omega, para conhecer mais sobre a arquitetura da plataforma, acesse o [Desenho de arquitetura da solução](https://omegaenergiarenovavel.sharepoint.com/sites/OMCDigital140/SitePages/Desenho-plataforma-Omega.aspx)

O projeto está organizado em uma arquitetura de camadas, seguindo [padrão de camadas](https://omegaenergiarenovavel.sharepoint.com/sites/OMCDigital140/SitePages/Camadas.aspx) adotado na Omega.

Detalhes da stack e integrações:
- A implementação é feita em [TypeScript](https://www.typescriptlang.org/) rodando sobre [Node 19](https://nodejs.org/).
- Uso do framework [NestJs 9.*](https://nestjs.com/).
- Persistência de dados é feita em um banco [PostgreSQL 14.*](https://www.postgresql.org/).
- Filas são gerenciadas utilizando o [Redis 7.*](https://redis.io/).
- As bibliotecas utilizadas pelo projeto podem ser vista nos arquivos que estão na raiz do projeto:
    - [package.json](package.json)

## Execução do projeto/sistema

### Via docker-compose

O projeto está configurado para execução com [docker-compose](https://docs.docker.com/compose/), onde já estão configuradas variáveis de ambiente e demais dependências.

#### Para rodar o projeto, utilize:

```bash
# Para subir a aplicação
docker-compose up app
```

```bash
# Para executar os testes
docker-compose up test
```

```bash
# Para executar acesso ao console e rodar qualquer comando NPM desejado
docker-compose run --rm console
```

```bash
# Para executar apenas as ferramentas auxiliares como banco de dados, cache, mensageria, etc...
docker-compose --profile tools up
```

### Localmente via nodejs:

Em ambiente local ou de testes, o serviço utiliza variáveis de ambiente que podem ser definidas no arquivo `.env`. 
Tal arquivo pode ser criado a partir do exemplo `.env.example`.

É obrigatório informar as envs (lembrando que via docker-compose isso não é necessário):
- DATABASE_URL: Exemplo `postgres://postgres:postgres@localhost:5432/myapp`.
- REDIS_HOST: Exemplo `localhost`
- REDIS_PORT: Exemplo `6379`

Sugere-se o uso de docker-compose para subir o banco de dados e o redis, através do comando:
```bash
# Para executar apenas as ferramentas auxiliares como banco de dados, cache, mensageria, etc...
docker-compose --profile tools up
```

#### Para rodar o projeto, utilize:

```bash
# Para subir a aplicação
npm run start
```

```bash
# Para executar os testes
npm run test
```
---
## Alterações, teste e validação

Toda alteração no código deve ser realizada respeitando o processo |DETALHAR|.

---

O testes automatizados são executados através da ferramenta [jest](https://jestjs.io/), e podem ser executados conforme instruções na seção anterior.

Para validar e chamar as API's manualmente acesse a página com o [Swagger](https://swagger.io/):
- Local: [http://localhost:3000/apidoc](http://localhost:3000/apidoc)

---

Para acesso aos ambientes onde o serviço está deployado, acesse: |DETALHAR|

## Atualização e monitoramento.

|DETALHAR|
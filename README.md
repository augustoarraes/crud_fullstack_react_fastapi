# FullStack Microsserviço CRUD: React JS e Python FastAPI

Uma Aplicação FullStack onde temos como frontend em React JS, backend em Python FastAPI e banco de dados Postgres.
- Pasta `fastapi_crud` é o backend da aplicação
- E, `frontend-react-produtos` é frontend da aplicação


## Subir a aplicação rápido

Antes de subir a aplicação, verificar as credenciais, principalmente do BD, no `compose.yml` e no `.env` do backend.

```bash
docker compose up -d

# caso o FastAPI não suba de imediato
docker restart fastapi_crud
# caso queira verificar o log de execução do microsserviço
docker logs -f fastapi_crud
```

Acessando a Aplicação FrontEnd [http://localhost:3000](http://localhost:3000)

Agora é so ver as rotas REST disponíveis para testar o backdend direto (Swagger da API): [http://127.0.0.1:5000/docs](http://127.0.0.1:5000/docs)

E opcional tem a monitoração do serviço: `http://127.0.0.1:9090`


## Opcional para quem estiver ingressando no FastAPI

- Makefile
- app/test_api.py
- prometheus.yml


## Rodar o Test

```bash
pytest
# ou
pytest --cov=api
```


## Boas Práticas na Codificação

Um bom pré-requisito é ter uma boa massa de dados, banco de dados local interessante para o consumo dos Endpoints.
Sempre avaliar as Regras de Negócio.

1. Sempre TESTE, regra das regras
2. Teste os Endpoints com campos vazios, diante às Regras de Negócio (RN)
3. Tratamento de Duplicidade em endpoints POST de inserção
4. Endpoints de Filtro de Consulta/Pesquisa:
4.1. Aceitar de campos nulos até cada campo para afinar o filtro da query
4.2. Fragmentar a Query a cada campo: `if campo: ... <parte da query filter SQLAlchemy>` 
4.3. De acordo com RN específicas de Filtro, operadores `or_` e `and_` do SQLAlchemy
4.4. Testar todas as possibilidades do Filtro
5. Retorne status code 400 para condições não atendidas


## Contato

Augusto Arraes
[site](http://linktr.ee/a.arraes)

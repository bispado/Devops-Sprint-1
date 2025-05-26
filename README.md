# MotoAPI

## Descrição do Projeto
API RESTful para gerenciamento de motos, integrando banco de dados Oracle e documentação via Swagger.

## Rotas

| Método | Rota           | Descrição                |
|--------|----------------|--------------------------|
| GET    | /api/motos     | Lista todas as motos     |
| GET    | /api/motos/{id}| Busca moto por ID        |
| POST   | /api/motos     | Cria uma nova moto       |
| PUT    | /api/motos/{id}| Atualiza uma moto        |
| DELETE | /api/motos/{id}| Remove uma moto          |

### Exemplo de Insert (POST)
```json
POST /api/motos
{
  "marca": "Honda",
  "modelo": "CB 500F",
  "ano": 2022,
  "cor": "Vermelha"
}
```
(Repita para 5 exemplos diferentes)

## Instalação

1. Clone o repositório:
   ```
   git clone https://github.com/seuusuario/MotoAPI.git
   cd MotoAPI
   ```
2. Configure a string de conexão Oracle no `appsettings.json`.
3. Restaure os pacotes e rode a aplicação:
   ```
   dotnet restore
   dotnet run
   ```

## Docker

Para rodar com Docker:
```bash
docker build -t motoapi .
docker run -p 5000:80 motoapi
```

## Documentação OpenAPI

Acesse [http://localhost:5000/swagger](http://localhost:5000/swagger) para visualizar a documentação interativa.

## Scripts Azure CLI

```bash
# Criação do grupo de recursos
az group create --name MotoAPIGroup --location eastus

# Criação do App Service Plan
az appservice plan create --name MotoAPIPlan --resource-group MotoAPIGroup --sku B1 --is-linux

# Criação do Web App
az webapp create --resource-group MotoAPIGroup --plan MotoAPIPlan --name MotoAPIApp --runtime "DOTNETCORE|6.0"

# Configuração de variáveis de ambiente (exemplo)
az webapp config appsettings set --resource-group MotoAPIGroup --name MotoAPIApp --settings ConnectionStrings__DefaultConnection="sua_string_oracle"
```

---

Se quiser, posso criar um arquivo `README.md` com esse conteúdo adaptado para o seu projeto, além de sugerir um `Dockerfile` e exemplos de scripts. Gostaria que eu faça isso? Se sim, me envie detalhes como:
- Descrição resumida do seu projeto
- Exemplo de 5 inserts (ou os dados das motos)
- Nome do usuário do GitHub (opcional, para o link)
- Alguma configuração específica do Oracle (host, porta, etc)

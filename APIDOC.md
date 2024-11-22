# Documentação da API - Projeto HUOLI

## Endpoints

### 1. Login de Cliente

- **URL**: `http://localhost:5000/login`
- **Método**: `POST`
- **Descrição**: Endpoint para autenticar um cliente no sistema.

#### Parâmetros da Requisição

- **Content-Type**: `application/json`
- **Body**: Um objeto JSON contendo as credenciais do cliente.

#### Tipos
- email: string
- senha: string

#### Exemplo de Requisição
```
POST http://localhost:5000/login
Content-Type: application/json

{
    "email": "joao.silva@email.com",
    "senha": "senhaJoao123"
}
```

- Retorno esperado em caso de sucesso: 200 (Login bem-sucedido)
- Retorno esperado em caso de erro: 400 (Parâmetros obrigatórios não fornecidos), 401 (Credenciais inválidas)

### 2. Cadastro de Cliente

- **URL**: `http://localhost:8080/cliente`
- **Método**: `POST`
- **Descrição**: Endpoint para cadastrar um novo cliente no sistema.

#### Parâmetros da Requisição

- **Content-Type**: `application/json`
- **Body**: Um objeto JSON contendo os dados do cliente.

#### Tipos
- nome: string
- email: string
- cpf: string
- telefone: string
- cep: string
- dtNascimento: string (Formato: `YYYY-MM-DD`)
- senha: string

#### Exemplo de Requisição
```
POST http://localhost:8080/cliente
Content-Type: application/json

{
    "nome": "João Silva",
    "email": "joao.silva@email.com",
    "cpf": "12345678901",
    "telefone": "(11) 98765-4321",
    "cep": "12345678",
    "dtNascimento": "1980-05-15",
    "senha": "senha123"
}
```

- Retorno esperado em caso de sucesso: 200 (Cliente cadastrado com sucesso)
- Retorno esperado em caso de erro: 400 (Erro na inserção dos dados)

### 3. Buscar Eletrodomésticos de Cliente

- **URL**: `http://localhost:5000/find-eletrodomesticos`
- **Método**: `GET`
- **Descrição**: Endpoint para buscar os eletrodomésticos cadastrados de um cliente específico pelo email.

#### Parâmetros da Requisição

- **Query Params**: `email` - Email do cliente cujos eletrodomésticos serão buscados.

#### Tipos
- email: string

#### Exemplo de Requisição
```
GET http://localhost:5000/find-eletrodomesticos?email=joao.silva@email.com
```

- Retorno esperado em caso de sucesso: 200 (Lista de eletrodomésticos do cliente)
- Retorno esperado em caso de erro: 404 (Cliente não encontrado)

### 4. Cadastro de Eletrodoméstico

- **URL**: `http://localhost:8080/eletrodomestico`
- **Método**: `POST`
- **Descrição**: Endpoint para cadastrar um novo eletrodoméstico no sistema.

#### Parâmetros da Requisição

- **Content-Type**: `application/json`
- **Body**: Um objeto JSON contendo os dados do eletrodoméstico.

#### Tipos
- idCliente: integer
- nome: string
- marca: string
- modelo: string
- potencia: integer
- voltagem: string
- tempoUso: integer
- custoEstimado: number

#### Exemplo de Requisição
```
POST http://localhost:8080/eletrodomestico
Content-Type: application/json

{
    "idCliente": 1,
    "nome": "Geladeira",
    "marca": "Electrolux",
    "modelo": "DF35X",
    "potencia": 150,
    "voltagem": "220V",
    "tempoUso": 120,
    "custoEstimado": 10.50
}
```

- Retorno esperado em caso de sucesso: 200 (Eletrodoméstico cadastrado com sucesso)
- Retorno esperado em caso de erro: 400 (Erro na inserção dos dados)

### 5. Atualizar Eletrodoméstico

- **URL**: `http://localhost:8080/eletrodomestico/{id}`
- **Método**: `PUT`
- **Descrição**: Endpoint para atualizar os dados de um eletrodoméstico específico pelo ID.

#### Parâmetros da Requisição

- **URL Params**: `{id}` - ID do eletrodoméstico a ser atualizado.
- **Content-Type**: `application/json`
- **Body**: Um objeto JSON com os dados atualizados do eletrodoméstico.

#### Tipos
- nome: string
- marca: string
- modelo: string
- potencia: integer
- voltagem: string
- tempoUso: integer
- custoEstimado: number

#### Exemplo de Requisição
```
PUT http://localhost:8080/eletrodomestico/1
Content-Type: application/json

{
    "nome": "Geladeira",
    "marca": "Electrolux",
    "modelo": "DF36X",
    "potencia": 150,
    "voltagem": "220V",
    "tempoUso": 130,
    "custoEstimado": 11.00
}
```

- Retorno esperado em caso de sucesso: 200 (Eletrodoméstico atualizado com sucesso)
- Retorno esperado em caso de erro: 404 (Eletrodoméstico não encontrado)

### 6. Deletar Eletrodoméstico

- **URL**: `http://localhost:8080/eletrodomestico/{id}`
- **Método**: `DELETE`
- **Descrição**: Endpoint para deletar um eletrodoméstico específico do sistema pelo ID.

#### Parâmetros da Requisição

- **URL Params**: `{id}` - ID do eletrodoméstico a ser deletado.

#### Exemplo de Requisição
```
DELETE http://localhost:8080/eletrodomestico/1
```

- Retorno esperado em caso de sucesso: 200 (Eletrodoméstico deletado com sucesso)
- Retorno esperado em caso de erro: 404 (Eletrodoméstico não encontrado)

### 7. Cadastro de Configuração de Consumo

- **URL**: `http://localhost:8080/configuracaoConsumo`
- **Método**: `POST`
- **Descrição**: Endpoint para cadastrar uma nova configuração de consumo para um eletrodoméstico.

#### Parâmetros da Requisição

- **Content-Type**: `application/json`
- **Body**: Um objeto JSON contendo os dados da configuração.

#### Tipos
- idEletrodomestico: integer
- limiteConsumo: integer
- acaoAposLimite: string

#### Exemplo de Requisição
```
POST http://localhost:8080/configuracaoConsumo
Content-Type: application/json

{
    "idEletrodomestico": 1,
    "limiteConsumo": 200,
    "acaoAposLimite": "alertar"
}
```

- Retorno esperado em caso de sucesso: 200 (Configuração cadastrada com sucesso)
- Retorno esperado em caso de erro: 400 (Erro na inserção dos dados)

### 8. Atualizar Configuração de Consumo

- **URL**: `http://localhost:8080/configuracaoConsumo/{id}`
- **Método**: `PUT`
- **Descrição**: Endpoint para atualizar uma configuração de consumo específica pelo ID.

#### Parâmetros da Requisição

- **URL Params**: `{id}` - ID da configuração a ser atualizada.
- **Content-Type**: `application/json`
- **Body**: Um objeto JSON com os dados atualizados da configuração.

#### Tipos
- limiteConsumo: integer
- acaoAposLimite: string

#### Exemplo de Requisição
```
PUT http://localhost:8080/configuracaoConsumo/1
Content-Type: application/json

{
    "limiteConsumo": 300,
    "acaoAposLimite": "desligar"
}
```

- Retorno esperado em caso de sucesso: 200 (Configuração atualizada com sucesso)
- Retorno esperado em caso de erro: 404 (Configuração não encontrada)

### 9. Deletar Configuração de Consumo

- **URL**: `http://localhost:8080/configuracaoConsumo/{id}`
- **Método**: `DELETE`
- **Descrição**: Endpoint para deletar uma configuração de consumo específica do sistema pelo ID.

#### Parâmetros da Requisição

- **URL Params**: `{id}` - ID da configuração a ser deletada.

#### Exemplo de Requisição
```
DELETE http://localhost:8080/configuracaoConsumo/1
```

- Retorno esperado em caso de sucesso: 200 (Configuração deletada com sucesso)
- Retorno esperado em caso de erro: 404 (Configuração não encontrada)
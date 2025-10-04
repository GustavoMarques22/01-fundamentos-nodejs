# Fundamentos Node.js

Este projeto é um estudo prático dos fundamentos do Node.js, implementando uma API REST simples para gerenciamento de usuários e explorando conceitos de streams.

## 📋 Sobre o Projeto

Este projeto demonstra os conceitos fundamentais do Node.js através da implementação de:

- **Servidor HTTP nativo** sem frameworks externos
- **Sistema de roteamento** customizado com parâmetros dinâmicos
- **Middleware** para parsing de JSON
- **Banco de dados em memória** com persistência em arquivo JSON
- **Streams** para processamento de dados
- **Módulos ES6** (import/export)

## 🚀 Tecnologias Utilizadas

- **Node.js** - Runtime JavaScript
- **HTTP Module** - Servidor web nativo
- **File System** - Manipulação de arquivos
- **Streams** - Processamento de dados em fluxo
- **Crypto** - Geração de UUIDs
- **ES6 Modules** - Sistema de módulos moderno

## 📁 Estrutura do Projeto

```
├── src/
│   ├── server.js              # Servidor HTTP principal
│   ├── routes.js              # Definição das rotas da API
│   ├── database.js            # Classe para gerenciamento de dados
│   ├── middlewares/
│   │   └── json.js            # Middleware para parsing de JSON
│   └── utils/
│       ├── build-route-path.js    # Construtor de regex para rotas
│       └── extract-query-params.js # Extrator de query parameters
├── streams/
│   ├── fundamentals.js        # Exemplos básicos de streams
│   ├── buffer.js              # Trabalhando com buffers
│   ├── stream-http-server.js  # Servidor HTTP com streams
│   └── fake-upload-to-http-stream.js # Upload simulado
├── db.json                    # Banco de dados JSON
└── package.json              # Configurações do projeto
```

## 🔧 Como Executar

1. **Instalar dependências:**
   ```bash
   npm install
   ```

2. **Executar em modo desenvolvimento:**
   ```bash
   npm run dev
   ```

3. **Acessar a API:**
   - Servidor rodará em `http://localhost:3333`

## 📚 API Endpoints

### Usuários

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/users` | Lista todos os usuários |
| `GET` | `/users?search=termo` | Busca usuários por nome ou email |
| `POST` | `/users` | Cria um novo usuário |
| `PUT` | `/users/:id` | Atualiza um usuário específico |
| `DELETE` | `/users/:id` | Remove um usuário específico |

### Exemplos de Uso

**Criar usuário:**
```bash
curl -X POST http://localhost:3333/users \
  -H "Content-Type: application/json" \
  -d '{"name": "João Silva", "email": "joao@email.com"}'
```

**Listar usuários:**
```bash
curl http://localhost:3333/users
```

**Buscar usuários:**
```bash
curl "http://localhost:3333/users?search=João"
```

**Atualizar usuário:**
```bash
curl -X PUT http://localhost:3333/users/ID_DO_USUARIO \
  -H "Content-Type: application/json" \
  -d '{"name": "João Santos", "email": "joao.santos@email.com"}'
```

**Deletar usuário:**
```bash
curl -X DELETE http://localhost:3333/users/ID_DO_USUARIO
```

## 🧠 Conceitos Demonstrados

### 1. Servidor HTTP Nativo
- Criação de servidor sem frameworks
- Manipulação de requisições e respostas
- Tratamento de métodos HTTP

### 2. Sistema de Roteamento
- Regex para matching de rotas
- Parâmetros dinâmicos (`:id`)
- Query parameters
- Middleware de parsing

### 3. Banco de Dados Simples
- Classe para CRUD operations
- Persistência em arquivo JSON
- Busca com filtros
- Operações assíncronas

### 4. Streams
- Readable, Transform e Writable streams
- Pipeline de processamento
- Buffers e encoding
- Processamento de dados em tempo real

### 5. Módulos ES6
- Import/export statements
- Módulos nativos do Node.js
- Organização de código

## 🔍 Arquivos de Estudo

### `src/server.js`
Servidor HTTP principal que:
- Cria instância do servidor
- Aplica middleware de JSON
- Encontra rotas correspondentes
- Extrai parâmetros e query strings
- Executa handlers das rotas

### `src/database.js`
Classe que implementa:
- CRUD completo (Create, Read, Update, Delete)
- Persistência em arquivo JSON
- Busca com filtros
- Operações assíncronas

### `src/routes.js`
Definição das rotas da API:
- GET `/users` - Listar usuários
- POST `/users` - Criar usuário
- PUT `/users/:id` - Atualizar usuário
- DELETE `/users/:id` - Deletar usuário

### `streams/fundamentals.js`
Exemplos de streams:
- `OneToHundredStream` - Stream de leitura
- `ReverseNumberStream` - Stream de transformação
- `MultiplyByTenStream` - Stream de escrita

## 🎯 Objetivos de Aprendizado

Este projeto visa demonstrar:

1. **Fundamentos do Node.js** sem dependências externas
2. **Arquitetura de APIs REST** simples
3. **Manipulação de dados** em JavaScript
4. **Conceitos de streams** para processamento eficiente
5. **Organização de código** com módulos ES6
6. **Tratamento de requisições HTTP** nativas

## 📝 Notas de Estudo

- O projeto usa **ES6 modules** (`"type": "module"` no package.json)
- O servidor roda na porta **3333** por padrão
- Os dados são persistidos no arquivo `db.json`
- O sistema de roteamento usa **regex** para matching
- Os **streams** demonstram processamento de dados em tempo real

## 🔄 Próximos Passos

Para evoluir este projeto, considere:

- Adicionar validação de dados
- Implementar autenticação/autorização
- Adicionar testes unitários
- Melhorar tratamento de erros
- Implementar logging
- Adicionar documentação da API (Swagger)
- Conectar com banco de dados real (PostgreSQL, MongoDB)

---

**Projeto desenvolvido para fins educacionais - Fundamentos Node.js**

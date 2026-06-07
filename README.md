# 🎬 Projeto Cinema - POO3 (P2)

![NestJS](https://img.shields.io/badge/Framework-NestJS-E0234E?logo=nestjs\&logoColor=white)
![Prisma](https://img.shields.io/badge/ORM-Prisma-2D3748?logo=prisma\&logoColor=white)
![SQLite](https://img.shields.io/badge/Database-SQLite-003B57?logo=sqlite\&logoColor=white)
![TypeScript](https://img.shields.io/badge/Language-TypeScript-3178C6?logo=typescript\&logoColor=white)

## 📖 Sobre o Projeto

Este projeto consiste no desenvolvimento de uma API REST para gerenciamento de um sistema de cinema, criada como atividade da disciplina de Programação Orientada a Objetos III (POO3).

O sistema permite realizar operações de cadastro, consulta, atualização e remoção (CRUD) dos seguintes módulos:

* Cinema
* Filme
* Sala
* Sessão
* Ingresso
* Lanche
* Pedido

A aplicação foi desenvolvida utilizando NestJS, Prisma ORM e SQLite.

---

## 🛠️ Tecnologias Utilizadas

* TypeScript
* NestJS
* Prisma ORM
* SQLite
* Node.js
* Postman

---

## 📂 Estrutura do Projeto

```text
src/
├── cinema/
├── filme/
├── sala/
├── sessao/
├── ingresso/
├── lanche/
├── pedido/
├── prisma/
└── main.ts
```

---

## 🚀 Instalação

Clone o repositório:

```bash
git clone https://github.com/Samyr-Dev/POO3_P2-Projeto_Cinema.git
```

Entre na pasta do projeto:

```bash
cd POO3_P2-Projeto_Cinema
```

Instale as dependências:

```bash
npm install
```

---

## ▶️ Executando o Projeto

Inicie o servidor em modo de desenvolvimento:

```bash
npm run start:dev
```

A aplicação estará disponível em:

```text
http://localhost:3001
```

---

## 🗄️ Banco de Dados

Executar migrations:

```bash
npx prisma migrate dev
```

Visualizar o banco utilizando Prisma Studio:

```bash
npx prisma studio --url file:./prisma/dev.db
```

---

## 🔄 Fluxo Correto dos Testes

Para evitar erros relacionados às chaves estrangeiras (Foreign Keys), recomenda-se seguir a seguinte ordem:

1. Criar Cinema
2. Criar Filme
3. Criar Sala
4. Criar Sessão
5. Criar Lanche
6. Criar Ingresso
7. Criar Pedido

---

## 📬 Endpoints da API

### 🏢 Cinema

| Método | Endpoint    |
| ------ | ----------- |
| GET    | /cinema     |
| GET    | /cinema/:id |
| POST   | /cinema     |
| PATCH  | /cinema/:id |
| DELETE | /cinema/:id |

Exemplo de criação:

```json
{
  "nome": "Cine Goiânia Shopping",
  "endereco": "Av. T-10, Setor Bueno"
}
```

---

### 🎬 Filme

| Método | Endpoint   |
| ------ | ---------- |
| GET    | /filme     |
| GET    | /filme/:id |
| POST   | /filme     |
| PATCH  | /filme/:id |
| DELETE | /filme/:id |

Exemplo de criação:

```json
{
  "titulo": "Interestelar",
  "diretor": "Christopher Nolan",
  "duracao": 169,
  "genero": "Ficção Científica"
}
```

---

### 🪑 Sala

| Método | Endpoint  |
| ------ | --------- |
| GET    | /sala     |
| GET    | /sala/:id |
| POST   | /sala     |
| PATCH  | /sala/:id |
| DELETE | /sala/:id |

Exemplo de criação:

```json
{
  "capacidade": 150,
  "tipoTela": "IMAX"
}
```

---

### ⏰ Sessão

| Método | Endpoint    |
| ------ | ----------- |
| GET    | /sessao     |
| GET    | /sessao/:id |
| POST   | /sessao     |
| PATCH  | /sessao/:id |
| DELETE | /sessao/:id |

Exemplo de criação:

```json
{
  "dataHora": "2026-06-07T21:00:00.000Z",
  "cinemaId": 1,
  "filmeId": 1,
  "salaId": 1
}
```

---

### 🎟️ Ingresso

| Método | Endpoint      |
| ------ | ------------- |
| GET    | /ingresso     |
| GET    | /ingresso/:id |
| POST   | /ingresso     |
| PATCH  | /ingresso/:id |
| DELETE | /ingresso/:id |

Exemplo de criação:

```json
{
  "preco": 35.90,
  "sessaoId": 1
}
```

---

### 🍿 Lanche

| Método | Endpoint    |
| ------ | ----------- |
| GET    | /lanche     |
| GET    | /lanche/:id |
| POST   | /lanche     |
| PATCH  | /lanche/:id |
| DELETE | /lanche/:id |

Exemplo de criação:

```json
{
  "nome": "Combo Grande",
  "preco": 29.90
}
```

---

### 🧾 Pedido

| Método | Endpoint    |
| ------ | ----------- |
| GET    | /pedido     |
| GET    | /pedido/:id |
| POST   | /pedido     |
| PATCH  | /pedido/:id |
| DELETE | /pedido/:id |

Exemplo de criação:

```json
{
  "ingressoId": 1,
  "lancheId": 1
}
```

---

## 📮 Collection Postman

A collection utilizada durante os testes pode ser adicionada ao repositório na pasta:

```text
/COLLECTIONS_JSON-POSTMAN/{modúloDesejado}.postman_collection.json
```

Para utilizá-la:

1. Abra o Postman.
2. Clique em **Import**.
3. Selecione o arquivo da collection.
4. Execute os testes dos endpoints.

---

## 📊 Relacionamentos

```text
Cinema
   │
   └── Sessão ─── Filme
         │
         ├── Sala
         │
         └── Ingresso
                 │
                 └── Pedido
                         │
                         └── Lanche
```

---

## 👨‍💻 Autores

* Pedro Lucas Ramos
* Samyr Silva

---

## 🔗 Repositório

https://github.com/Samyr-Dev/POO3_P2-Projeto_Cinema

---

## 📄 Licença

Este projeto foi desenvolvido para fins acadêmicos na disciplina de Programação Orientada a Objetos III (POO3).

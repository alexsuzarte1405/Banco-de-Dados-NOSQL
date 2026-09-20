# Banco-de-Dados-NOSQL
Introdução - NoSQL / Mongo DB
Definição
O que é NoSQL?
• NoSQL é um paradigma de banco de dados que englob
adiversos tipos de bancos de dados não relacionais.
Projetados para oferecer:
▪ Flexibilidade
▪ Escalabilidade
▪ Alto desempenho.

<img width="389" height="233" alt="image" src="https://github.com/user-attachments/assets/fe7b287e-0c49-4a63-90dd-8d5154444c9d" />

Os quatro principais paradigmas de bancos de dados
NoSQL são:
• Bancos de dados orientados a documentos (ex.:
MongoDB)
• Bancos de dados chave-valor (ex.: Redis)
• Bancos de dados de famílias de colunas (wide-
column) (ex.: Cassandra)
• Bancos de dados orientados a grafos (ex.: Neo4j)

# O que é MongoDB?
• O que significa "Mongo"?
o Humongous (Gigante) — o MongoDB foi projetado para
armazenar e gerenciar grandes volumes de dados de forma
eficiente.
• MongoDB é um banco de dados NoSQL de código aberto,
orientado a documentos, projetado para armazenar e gerenciar
grandes quantidades de dados de maneira eficiente.
• Diferentemente dos bancos de dados relacionais tradicionais
(como MySQL ou PostgreSQL), o MongoDB armazena os dados em
documentos, em vez de linhas em tabelas.

Como o MongoDB funciona?
• Um servidor MongoDB pode hospedar múltiplos bancos de dados.
• Cada banco de dados contém coleções (collections), e cada coleção
armazena documentos (documents).
<img width="313" height="157" alt="image" src="https://github.com/user-attachments/assets/a80d8581-5577-4cf5-a0ca-4371f3bc4265" />

JSON (BSON) Data Format
• Todo registro no MongoDB é, na verdade, um
documento.
• Os documentos são armazenados no MongoDB em um
formato semelhante ao JSON, chamado BSON (Binary
JSON).
• Os documentos BSON são objetos que contêm uma
lista ordenada dos elementos que armazenam.
• Cada elemento é composto por um nome de campo
(field name) e um valor de um determinado tipo.

# Formato JSON / BSON (Binary JSON)
<img width="500" height="227" alt="image" src="https://github.com/user-attachments/assets/20ecbd30-ea8b-4def-9e9b-fece0616365a" />

# Relacionamentos
• Diferentemente dos bancos de dados relacionais, o
MongoDB minimiza o uso de relacionamentos entre
coleções.
• Em vez de dividir os dados relacionados em várias
tabelas e depois uni-los por meio de JOINs, o MongoDB
geralmente armazena esses dados juntos no mesmo
documento utilizando documentos incorporados
(embedded documents).

# MongoDB Ecosistema
<img width="498" height="225" alt="image" src="https://github.com/user-attachments/assets/0fb4ff30-0824-4316-be3e-8d0ccc1bf1fd" />

# Comandos Principais...
• mongosh
• show databases / show dbs
• use shop
• show collections
• db.<collection_name>.insertOne({<object>>})
• db.createCollection("<collection_name>")
• db.<collection_name>.find()

# Introdução - CRUD
Databases, Collections, Documents
<img width="308" height="188" alt="image" src="https://github.com/user-attachments/assets/461472e0-5985-4e50-af79-349583b34515" />

# JSON
• "name": "jefté" é chamado de campo (field) ou
propriedade (property) do documento JSON.
Múltiplos campos são separados por vírgulas.
• Os campos (fields) são compostos por uma
chave (key), também chamada de nome
(name), e um valor (value). A chave e o valor
são separados por dois-pontos (:).
• Os valores (values) podem ser strings (por
exemplo, "Jefté"), números (por exemplo,
35), booleanos (por exemplo, true), arrays ([
... ]) e outros documentos (também
chamados de objetos; { ... }).

<img width="257" height="224" alt="image" src="https://github.com/user-attachments/assets/65fb6d46-043b-4996-8222-ecc808862b23" />

# CRUD
<img width="444" height="230" alt="image" src="https://github.com/user-attachments/assets/37be8ee8-f92b-4a24-9944-d515fc295e58" />


# Anotações e Comandos Básico - MongoDB

Guia prático de comandos básicos do MongoDB.

---

## 💻 Comandos Básicos

### 1. Gerenciamento de Bancos e Collections

```javascript
// Exibir todos os bancos de dados
show databases

// Selecionar ou criar um banco de dados
use loja_informatica

// Criar uma nova collection explicitamente
db.createCollection("cliente")

// Mostrar todas as collections do banco atual
show collections


### Inserção de documentos:

// Inserir apenas 1 documento (objeto)
db.cliente.insertOne({
  "nome": "jefté",
  "idade": 35,
  "pets": ["dora", "sabrina"],
  "endereco": {
    "logradouro": "Sossego"
  }
})

// Inserir múltiplos documentos de uma vez
db.cliente.insertMany([
  { "nome": "Brenno" },
  { "nome": "João" },
  { "nome": "Maria" },
  { "nome": "José" },
  { "nome": "Noé" }
])


### Consultar Documentos: 

// Listar todos os documentos da collection
db.cliente.find()

// Buscar documentos por um campo específico
db.cliente.find({ "nome": "José" })

// Buscar por identificador único (_id)
db.cliente.find({ _id: ObjectId('6a7bbab007ff2cf8649f68a9') })
```

# MongoDB: Modelagem & Schemas
## Identificadores Únicos, Tipos de Dados, Projeções e Padrões Avançados de
Relacionamento (1:1, 1:N, N:M)

## IDs Únicos & Documentos Incorporados

### 1. IDs Únicos (_id)
Todo documento no MongoDB DEVE possuir obrigatoriamente um
campo _id.
- O MongoDB gera automaticamente um ObjectId() de 12 bytes.
- Você pode definir qualquer valor customizado para o _id.
<img width="292" height="58" alt="image" src="https://github.com/user-attachments/assets/ab398b98-49f0-4308-8fe0-2fe34be16365" />

### 2. Documentos Incorporados
Permitem armazenar dados relacionados diretamente dentro do
documento principal.
- Elimina a necessidade de junções de tabelas (joins) custosas.
- Excelente desempenho para dados que pertencem juntos.
- Exemplo: Dados de endereço mantidos no perfil do cliente.

## IDs Únicos & Embedded Documents (Documentos Incorporados)
### 3. IDs Únicos (_id)
Todo documento no MongoDB DEVE possuir obrigatoriamente um
campo _id.
- O MongoDB gera automaticamente um ObjectId() de 12 bytes.
- Você pode definir qualquer valor customizado para o _id.
<img width="235" height="54" alt="image" src="https://github.com/user-attachments/assets/77c47814-e5de-4e05-8159-9c42bf963f9b" />

### 4. Documentos Incorporados
- Permitem armazenar dados relacionados diretamente dentro do
documento principal.
- Elimina a necessidade de junções de tabelas (joins) custosas.
- Excelente desempenho para dados que pertencem juntos.
- Exemplo: Dados de endereço mantidos no perfil do cliente.
<img width="317" height="237" alt="image" src="https://github.com/user-attachments/assets/9722528c-1bf7-4409-9dbc-e1eda1f6d10e" />

## Projeção & Flexibilidade de Schema  
### 5. Projeção (Projection)
Define quais campos devem ser retornados em uma consulta de busca.
- Evita carregar o documento completo pela rede.
- Seleciona apenas os atributos estritamente necessários.
- Economiza largura de banda e memória da aplicação.
  
### 6. Sem Schema Rígido?
O MongoDB não impõe schemas estáticos a nível de banco de dados.
- Documentos da mesma coleção podem ter estruturas distintas.
- Permite evolução rápida do modelo sem rotinas pesadas de
migração.
- A aplicação pode impor validações flexíveis usando JSON Schema.

<img width="292" height="242" alt="image" src="https://github.com/user-attachments/assets/8cc05668-dc43-4f10-a5ca-5328a3b512bc" />

## Flexibilidade de Schema

### 7. O MongoDB não é justamente conhecido por NÃO exigir schemas de dados?
- O MongoDB não impõe um schema rígido! Os
documentos dentro de uma mesma collection não
precisam necessariamente seguir o mesmo schema.

- Porém, isso não significa que você não possa
utilizar algum tipo de schema.

## To Schema Or Not To Schema (Esquematizar ou não esquematizar)
<img width="585" height="299" alt="image" src="https://github.com/user-attachments/assets/85382dea-4bee-48ea-9aa6-40c5b57fcbce" />

## Tipos de Dados Suportados
<img width="653" height="185" alt="image" src="https://github.com/user-attachments/assets/9d671fda-c70f-4113-9d81-abe1c5d282a0" />

## Modelagem: Perguntas Essenciais
### Perguntas de Arquitetura
- Quais dados são necessários? Define os campos e como eles se relacionam.
- Onde o dado é consumido? Define as coleções e os agrupamentos de
campos.
- Qual o tipo de exibição? Determina as consultas mais eficientes.
- Qual a frequência de leitura/escrita? Define se a otimização focará em
buscas rápidas ou gravações sem duplicação.

<img width="313" height="212" alt="image" src="https://github.com/user-attachments/assets/54e3c66d-7f8a-464d-8319-68be98f48454" />

# Estratégias: Leitura vs. Escrita

---

## Muitas Consultas (Read-Heavy)

* **Objetivo:** Armazenar o dado pronto no formato exigido pelo Frontend.
* Evita transformações e agregações complexas em tempo de execução.
* Prioriza o uso de **Documentos Incorporados**.
* Ideal para catálogos de produtos e páginas iniciais.

### 💻 Exemplo Prático (Documentos Incorporados)
```json
{
  "_id": "66e123456789abcdef000001",
  "nome": "Notebook Gamer X",
  "preco": 4999.90,
  "estoque": 15,
  "detalhes_tecnicos": {
    "processador": "Intel i7",
    "memoria": "16GB RAM",
    "armazenamento": "512GB SSD"
  },
  "avaliacoes": [
    {
      "usuario": "Ana",
      "nota": 5,
      "comentario": "Excelente desempenho!"
    }
  ]
}
```

---

## Muitas Gravações (Write-Heavy)

* **Objetivo:** Armazenar o dado sem duplicações ou redundâncias.
* Garante atualizações rápidas em um único local.
* Prioriza o uso de **Referências (ObjectIds)**.
* Ideal para registros financeiros, pedidos e logs em tempo real.

### 💻 Exemplo Prático (Referências)

#### Coleção: `usuarios`
```json
{
  "_id": "55fa123456789abcdef00001",
  "nome": "João Silva",
  "email": "joao@email.com"
}
```

#### Coleção: `pedidos`
```json
{
  "_id": "99bc123456789abcdef00002",
  "data_pedido": "2026-09-20T12:00:00Z",
  "usuario_id": "55fa123456789abcdef00001", 
  "valor_total": 150.00,
  "status": "Processando"
}
```

## Relações: Embedded Documents vs References
<img width="548" height="263" alt="image" src="https://github.com/user-attachments/assets/24ed6f45-10bf-42ae-8542-19f869d3db98" />

# Relações 1:1 (Um para Um)

---

## Exemplo #1 — Paciente ↔ Doença

* **Abordagem:** Documento Incorporado
* Os dados pertencem exclusivamente ao paciente e são lidos juntos.

```javascript
db.patients.insertOne({
  name: "Jefté",
  age: 35,
  diseaseSummary: {
    diseases: ["cold", "broken leg"]
  }
})
```

---

## Exemplo #2 — Pessoa ↔ Carro

* **Abordagem:** Referência via ObjectId
* As entidades possuem vida independente na aplicação.

```javascript
db.persons.insertOne({
  _id: ObjectId("5b9..."),
  name: "Jefté",
  age: 35
})

db.cars.insertOne({
  model: "BMW",
  owner: ObjectId("5b9...")
})
```

<img width="654" height="93" alt="image" src="https://github.com/user-attachments/assets/31c10b84-162e-47cd-a54a-ba7d93c31394" />

# Relações 1:N (Um para Muitos)

---

## Exemplo #3 — Tópico ↔ Respostas

* **Abordagem:** Documento Incorporado
* Respostas são contidas no próprio fórum de discussão.

```javascript
db.questionThreads.insertOne({
  creator: "Jefté",
  question: "How does that work?",
  answers: [
    { text: "Like that." },
    { text: "Thanks!" }
  ]
})
```

---

## Exemplo #4 — Cidade ↔ Cidadãos

* **Abordagem:** Referência via ObjectId
* Evita estourar o limite de 16MB caso haja milhões de cidadãos.

```javascript
db.cities.insertOne({
  _id: ObjectId("5b9..."), name: "NYC"
})

db.citizens.insertMany([
  { name: "Jefté", cityId: ObjectId("5b9...") },
  { name: "Brenno", cityId: ObjectId("5b9...") }
])
```
<img width="616" height="133" alt="image" src="https://github.com/user-attachments/assets/18d76f4c-fc8e-455f-a557-df5efb7051e0" />

# Relações N:M (Muitos para Muitos)

---

## Exemplo #5 — Clientes ↔ Produtos

* **Abordagem:** Documento Incorporado (Pedidos)
* O histórico de pedidos é congelado dentro do cliente.

```javascript
db.customers.updateOne({}, {
  \$set: {
    orders: [{
      title: "A Book",
      price: 12.99,
      quantity: 2
    }]
  }
})
```

---

## Exemplo #6 — Livros ↔ Autores

* **Abordagem:** Array de Referências
* Autores e Livros possuem relacionamentos cruzados.

```javascript
db.books.updateOne({}, {
  \$set: {
    authors: [
      ObjectId("5b98d9e44d01c52e1637a9a6"),
      ObjectId("5b98d9e44d01c52e1637a9a7")
    ]
  }
})
```
<img width="589" height="128" alt="image" src="https://github.com/user-attachments/assets/e58a9d92-efb7-4eff-a0c0-b764a2fbee27" />

# Comparativo: Embedded vs. References

| Característica | Documentos Incorporados (Embedded) | Referências (References) |
| :--- | :--- | :--- |
| **Organização** | Agrupa os dados logicamente no mesmo documento. | Divide os dados entre coleções distintas. |
| **Caso de Uso** | Dados pertencentes juntos que não se sobrepõem. | Dados compartilhados ou com existência autônoma. |
| **Desempenho** | Excelente para leitura (consulta única sem joins). | Evita duplicação de escrita e otimiza atualizações. |
| **Limitações** | Atenção ao limite máximo de 16MB por documento. | Exige consultas adicionais ou estágio \$lookup. |


# Regra Prática para Tomada de Decisão

---

### Use Embedded
Quando os dados forem acessados juntos, houver forte relação de pertencimento, os dados não forem compartilhados e o tamanho total do documento estiver sob controle.

---

### Use References
Quando os dados forem compartilhados entre várias entidades, possuírem vida independente, os documentos puderem crescer sem limite fixo ou houver relação N:M complexa.

---

### Ajuste Fino
Modele a estrutura considerando o comportamento real de uso do sistema: equilibre a taxa de Leitura (Read) vs. Escrita (Write) da sua aplicação.




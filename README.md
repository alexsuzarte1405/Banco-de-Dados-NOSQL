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

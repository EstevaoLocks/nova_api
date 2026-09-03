<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=009688&center=true&vCenter=true&width=600&lines=API+de+Livros+%F0%9F%93%9A;FastAPI+%2B+MySQL+%2B+SQLAlchemy;CRUD+completo+do+zero+ao+Front+End" alt="Typing SVG" />

### 🧑‍💻 SW-II · Sistemas Web II · 3º Bimestre

**Uma API REST para gerenciamento de livros — do banco de dados à interface web.**

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=python&logoColor=white)](https://www.sqlalchemy.org/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=111111)](https://developer.mozilla.org/docs/Web/JavaScript)

<br/>

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow?style=flat-square)
![License](https://img.shields.io/badge/licença-MIT-blue?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/estevaolocks/nova_api?style=flat-square&color=009688)
![Repo Size](https://img.shields.io/github/repo-size/estevaolocks/nova_api?style=flat-square&color=blueviolet)

</div>

<br/>

## 📖 Sobre o projeto

> 🎓 Atividade avaliativa da disciplina de **Sistemas Web II**, com o objetivo de construir, em etapas práticas, uma aplicação completa para gerenciamento de livros — API, banco de dados e interface web.

Cada livro cadastrado possui:

| Campo | Tipo | Descrição |
| :--: | :--: | --- |
| 🆔 `id` | `int` | Identificador único, gerado automaticamente |
| 📕 `titulo` | `str` | Título do livro |
| ✍️ `autor` | `str` | Autor do livro |
| 📅 `ano_publicacao` | `int` | Ano de publicação |
| 📗 `disponivel` | `bool` | Situação de disponibilidade |

<br/>

## 🗂️ Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Arquitetura](#%EF%B8%8F-arquitetura)
- [Stack utilizada](#%EF%B8%8F-stack-utilizada)
- [Como rodar o projeto](#-como-rodar-o-projeto)
- [Endpoints da API](#-endpoints-da-api)
- [Estrutura de pastas](#-estrutura-de-pastas)
- [Roadmap](#-roadmap)
- [Estatísticas](#-estatísticas-do-repositório)
- [Autor](#-autor)

<br/>

## ✨ Funcionalidades

CRUD completo, com validação de dados e tratamento de erros HTTP:

| | Operação | Método | Rota | Descrição |
| :--: | --- | :--: | --- | --- |
| 🟢 | **Create** | `POST` | `/livros` | Cadastra um novo livro |
| 🔵 | **Read** | `GET` | `/livros` | Lista todos os livros |
| 🔵 | **Read** | `GET` | `/livros/{id}` | Consulta um livro específico |
| 🟠 | **Update** | `PUT` | `/livros/{id}` | Atualiza os dados de um livro |
| 🔴 | **Delete** | `DELETE` | `/livros/{id}` | Remove um livro |

<br/>

## 🏗️ Arquitetura

```mermaid
flowchart LR
    A[🌐 Front End<br/>HTML · CSS · JS] -- fetch() --> B[⚡ FastAPI<br/>Rotas & Validação]
    B -- SQLAlchemy ORM --> C[(🗄️ MySQL<br/>biblioteca_db)]
    C -- phpMyAdmin --> D[🛠️ XAMPP]

    style A fill:#F7DF1E,stroke:#333,color:#111
    style B fill:#009688,stroke:#333,color:#fff
    style C fill:#4479A1,stroke:#333,color:#fff
    style D fill:#FB7A24,stroke:#333,color:#fff
```

<br/>

## ⚙️ Stack utilizada

<div align="center">

| Camada | Tecnologias |
| --- | --- |
| **Back End** | Python · FastAPI · Uvicorn · Pydantic |
| **Banco de Dados** | MySQL · SQLAlchemy · PyMySQL · XAMPP · phpMyAdmin |
| **Front End** | HTML5 · CSS3 · JavaScript (Fetch API) |
| **Ferramentas** | VS Code · Git & GitHub · Postman/Insomnia |

</div>

<br/>

## 🚀 Como rodar o projeto

<details>
<summary><b>1️⃣ Clone o repositório</b></summary>

```bash
git clone https://github.com/estevaolocks/nova_api.git
cd nova_api
```
</details>

<details>
<summary><b>2️⃣ Crie e ative o ambiente virtual</b></summary>

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate
```
</details>

<details>
<summary><b>3️⃣ Instale as dependências</b></summary>

```bash
pip install -r requirements.txt
```
</details>

<details>
<summary><b>4️⃣ Configure o banco de dados</b></summary>

1. Inicie o **Apache** e o **MySQL** pelo XAMPP;
2. Acesse o **phpMyAdmin** e importe o arquivo `database/biblioteca_db.sql`;
3. Crie o arquivo `.env` na raiz do projeto:

```env
DB_USER=root
DB_PASSWORD=
DB_HOST=localhost
DB_PORT=3306
DB_NAME=biblioteca_db
```
</details>

<details>
<summary><b>5️⃣ Execute a aplicação</b></summary>

```bash
uvicorn main:app --reload
```

Acesse a documentação interativa em:

```
http://127.0.0.1:8000/docs
```
</details>

<br/>

## 📡 Endpoints da API

```http
GET     /                     → status da API
POST    /livros                → cadastra um livro
GET     /livros                → lista todos os livros
GET     /livros/{id}           → busca um livro pelo id
PUT     /livros/{id}           → atualiza um livro
DELETE  /livros/{id}           → exclui um livro
```

<br/>

## 📁 Estrutura de pastas

```
📦 api-de-livros
├── 📂 database/
│   └── biblioteca_db.sql
├── 📂 static/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── 📂 app/
│   ├── main.py
│   ├── models.py
│   ├── schemas.py
│   └── database.py
├── requirements.txt
├── .env.example
└── README.md
```

<br/>

## 🧭 Roadmap

- [x] 🟦 Fundação — ambiente, dependências e conexão com o MySQL
- [x] 🟩 Modelo `Livro`, schemas e rotas `POST` / `GET`
- [ ] 🟧 Rotas `PUT` / `DELETE` e tratamento de erros
- [ ] 🟥 Interface web completa (HTML, CSS, JavaScript)

<br/>

## 👤 Autor

<div align="center">

<img src="https://github.com/estevaolocks.png" width="100" style="border-radius: 50%;" alt="Foto de perfil"/>

**Estevão Locks**

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/estevaolocks)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/estevao-locks)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:estevao.locks11@gmail.com)

<br/>

<img src="https://komarev.com/ghpvc/?username=estevaolocks&label=Visualizações+do+perfil&color=009688&style=flat" alt="Visitor Badge"/>

---

**📚 Projeto desenvolvido para a disciplina de Sistemas Web II · 3º Bimestre**

<sub>Feito com ☕, FastAPI e algumas queries SQL teimosas.</sub>

</div>
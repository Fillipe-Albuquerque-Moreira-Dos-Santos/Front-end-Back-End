# 💼 Desafio Técnico – Sistema de Cadastro de Clientes

## 📘 Descrição

Este projeto é uma solução para o desafio de implementar um sistema de **cadastro de clientes**, com as funcionalidades de criar, editar, listar e excluir **clientes e logradouros**. A aplicação utiliza:

- Frontend: **JSF + PrimeFaces**, HTML, CSS, JavaScript
- Backend: **Spring Boot (Java 8)**
- Banco de Dados: **SQL Server 2022** (executado via Docker)
- IDE recomendada: Eclipse ou IntelliJ
- Gerenciador de banco: **DBeaver**

---

## 📐 Arquitetura da Solução

### Backend
- Spring Boot com Java 8
- API RESTful
- JPA (Hibernate) para mapeamento de entidades
- SQL Server 2022 para persistência dos dados
- Autenticação HTTP Basic

### Frontend
- JSF (JavaServer Faces)
- PrimeFaces
- HTML, CSS, JS
- Servidor de aplicação: WildFly 26 (Java EE)

---

## 🧱 Modelagem de Dados

```sql
CREATE TABLE Cliente (
    id_cliente INT PRIMARY KEY IDENTITY,
    nome VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    logotipo VARBINARY(MAX)
);

CREATE TABLE Logradouro (
    id_logradouro INT PRIMARY KEY IDENTITY,
    id_cliente INT,
    logradouro VARCHAR(255) NOT NULL,
    FOREIGN KEY (id_cliente) REFERENCES Cliente(id_cliente)
);

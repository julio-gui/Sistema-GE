# Sistema de Gestão de Estoque (Sistema-GE)

Este projeto é um microserviço de **gestão de estoque**, desenvolvido como parte da disciplina de **Programação Orientada a Objetos** no curso de **Análise e Desenvolvimento de Sistemas**. O objetivo principal é aplicar os conceitos de orientação a objetos e arquitetura de software moderna utilizando **Java com Spring Boot**.

## ✨ Funcionalidades

- Cadastro e gerenciamento de produtos
- Atualização de quantidades em estoque
- Remoção de produtos
- Consulta de produtos por ID ou listagem geral
- Autenticação com JWT
- Documentação da API com Swagger/OpenAPI
- Logs de requisições e operações

---

## 🛠️ Tecnologias Utilizadas

- Java 17
- Spring Boot 3.3.2
  - Spring Web
  - Spring Security + JWT
  - Spring Data JPA
  - Spring Validation
- PostgreSQL
- Lombok
- Swagger/OpenAPI
- H2 (para testes)
- Mockito (testes unitários)
- Apache Commons IO

---

## 🧩 Estrutura do Projeto

```
src/
├── main/
│   ├── java/
│   │   └── org/educadventista/sistemage/
│   │       ├── controller/
│   │       ├── model/
│   │       ├── repository/
│   │       ├── service/
│   │       ├── security/
│   │       └── SistemaGeApplication.java
│   └── resources/
│       ├── application.properties
│       └── static/
└── test/
```

---

## 📦 Executando o Projeto

### Requisitos
- Java 17
- Maven

### Rodando localmente

```bash
# Clone o repositório
git clone https://github.com/seuusuario/Sistema-GE.git
cd Sistema-GE

# Build
mvn clean install

# Executar
mvn spring-boot:run
```

API disponível em:  
`http://localhost:8080`

Swagger UI disponível em:  
`http://localhost:8080/swagger-ui.html`

---

## 🔐 Segurança

Este projeto implementa autenticação via JWT. Para acessar os endpoints protegidos:

1. Realize o login no endpoint de autenticação e receba o token JWT.
2. Inclua o token no cabeçalho das requisições seguintes:  
   ```
   Authorization: Bearer <seu_token>
   ```

---

## 📚 Endpoints da API

### 🔑 Autenticação

| Método | Endpoint        | Descrição                     |
|--------|------------------|-------------------------------|
| POST   | `/auth/login`   | Autentica usuário e retorna token JWT |

### 📦 Produtos

| Método | Endpoint           | Descrição                              |
|--------|---------------------|------------------------------------------|
| GET    | `/produtos`         | Lista todos os produtos                 |
| GET    | `/produtos/{id}`    | Busca produto por ID                    |
| POST   | `/produtos`         | Cadastra novo produto                   |
| PUT    | `/produtos/{id}`    | Atualiza os dados de um produto         |
| DELETE | `/produtos/{id}`    | Remove um produto                       |

### 📊 Estoque

| Método | Endpoint                     | Descrição                                       |
|--------|-------------------------------|--------------------------------------------------|
| PATCH  | `/estoque/{id}/entrada`       | Adiciona quantidade ao estoque do produto       |
| PATCH  | `/estoque/{id}/saida`         | Remove quantidade do estoque do produto         |
| GET    | `/estoque/{id}`               | Consulta o estoque de um produto específico     |

> ⚠️ Os endpoints protegidos exigem token JWT.

---

## ⚙️ Configuração do Banco de Dados

Exemplo do `application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://<host>:<port>/<database>
spring.datasource.username=<usuario>
spring.datasource.password=<senha>
spring.jpa.hibernate.ddl-auto=update
```

> A aplicação está preparada para uso com PostgreSQL em produção e H2 para testes.

---

## 👨‍💻 Autor

Julio Guilherme do Nascimento Batista  
Aluno de Análise e Desenvolvimento de Sistemas – UNASP

---

## 🧾 Licença

Este projeto foi desenvolvido exclusivamente para fins educacionais.


# APS Final - Spring Boot Application

Este projeto é uma aplicação Spring Boot que expõe APIs REST para gerenciar cursos, categorias, atividades e fotos.

## Pré-requisitos

Antes de iniciar, certifique-se de que você tem as seguintes ferramentas instaladas:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- Ferramenta para testar APIs (Swagger, Insomnia ou Thunder Client)

---

## 🚀 Como executar a aplicação

### Passo 1: Clone o repositório

```bash
git https://github.com/HenriqueGalvim/trabalho-final.git
cd aps-final
```

### Passo 2: Inicie o ambiente com Docker

Certifique-se de que o Docker está instalado e rodando. Em seguida, execute:

```bash
docker-compose up -d
```

> 📌 Este comando:
> - Faz o build do projeto usando o Docker.
> - Sobe o container da aplicação na porta **8080**.

---

## 🌐 Acesso aos serviços

### Passo 3: Verifique se a aplicação está rodando

Abra o navegador e acesse:
```text
http://localhost:8080
```

Você verá a mensagem padrão do Spring Boot.

---

### Passo 4: Acesse a documentação Swagger

O Swagger UI está disponível para explorar e testar as APIs. Acesse:
```text
http://localhost:8080/swagger-ui/index.html
```

No Swagger, você pode:
1. Navegar pelos endpoints.
2. Executar testes diretamente pela interface.
3. Ver a documentação detalhada de cada endpoint.

---

## 🔍 Testando com ferramentas de API

Se preferir usar ferramentas como **Insomnia** ou **Thunder Client**, siga os passos abaixo.

### Configuração das ferramentas de API

#### Endpoint base:
```text
http://localhost:8080
```

#### Estrutura dos endpoints:

- **Cursos**
  - `GET /cursos`: Lista todos os cursos.
  - `POST /cursos`: Cria um curso (exemplo de corpo JSON abaixo).
- **Categorias**
  - `GET /categorias`: Lista todas as categorias.
  - `POST /categorias`: Cria uma categoria.
- **Atividades**
  - `GET /atividades`: Lista todas as atividades.
  - `POST /atividades`: Cria uma atividade.
- **Fotos**
  - `GET /fotos`: Lista todas as fotos.
  - `POST /fotos`: Cria uma foto.

---

### Passo a passo para teste

#### 1. Testando com Insomnia

1. Abra o Insomnia.
2. Crie uma nova Workspace.
3. Adicione uma nova requisição:
   - **Método:** Escolha entre `GET`, `POST`, etc.
   - **URL:** Use um dos endpoints acima, ex.: `http://localhost:8080/cursos`.
   - **Body (para POST):** 
     ```json
     {
       "nome": "Curso de Teste"
     }
     ```

4. Clique em "Send" e verifique a resposta.

#### 2. Testando com Thunder Client (VS Code)

1. Instale a extensão [Thunder Client](https://www.thunderclient.com/) no Visual Studio Code.
2. Abra o projeto no VS Code.
3. Clique no ícone do Thunder Client na barra lateral.
4. Crie uma nova requisição:
   - **Método:** Escolha entre `GET`, `POST`, etc.
   - **URL:** Use um dos endpoints acima, ex.: `http://localhost:8080/categorias`.
   - **Body (para POST):**
     ```json
     {
       "nomeCategoria": "Categoria de Teste"
     }
     ```

5. Clique em "Send" para testar.

---

### Exemplo de Corpo para Criar Entidades

#### Criar Curso (`POST /cursos`)
```json
{
  "nome": "Curso de Teste"
}
```

#### Criar Categoria (`POST /categorias`)
```json
{
  "nomeCategoria": "Categoria de Teste"
}
```

#### Criar Atividade (`POST /atividades`)
```json
{
  "nome": "Atividade de Teste",
  "objetivo": "Aprender a testar APIs",
  "publicoAlvo": "Estudantes",
  "publicada": true,
  "data": "2024-12-20",
  "idCategoria": 1,
  "idCurso": 1
}
```

#### Criar Foto (`POST /fotos`)
```json
{
  "url": "https://exemplo.com/foto.jpg",
  "legenda": "Legenda da Foto",
  "idAtividade": 1
}
```

---

## 🛠️ Problemas comuns e soluções

### Problema 1: `docker-compose up` dá erro

- Certifique-se de que o Docker e o Docker Compose estão instalados.
- Limpe o cache do Docker:
  ```bash
  docker system prune -f
  docker builder prune -f
  ```

### Problema 2: Não consigo acessar o Swagger

- Verifique se a aplicação está rodando na porta correta:
  ```bash
  http://localhost:8080/swagger-ui/index.html
  ```

### Problema 3: Erro ao criar entidades no banco

- Certifique-se de que o corpo JSON está correto.
- Verifique se as IDs passadas (ex.: `idCategoria` e `idCurso`) existem no banco.

---

## 📚 Documentação adicional

Para mais detalhes sobre a estrutura do projeto ou dúvidas sobre endpoints, veja:

- [Documentação oficial do Spring Boot](https://spring.io/projects/spring-boot)
- [Docker Compose Reference](https://docs.docker.com/compose/)

## 🧑‍💻 Autor

- [Henrique Galvim](https://github.com/seu-usuario)

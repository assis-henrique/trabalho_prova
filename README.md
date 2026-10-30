# 📱 Sistema de Assistência Técnica de Celulares

## 📌 Sobre o Projeto

Este projeto consiste no desenvolvimento de um sistema informatizado para uma **assistência técnica de celulares**, com o objetivo de organizar e facilitar o gerenciamento de clientes, aparelhos e agendamentos de reparos.

O sistema foi desenvolvido para solucionar problemas causados pelo controle manual das informações, como perda de horários, duplicidade de dados, dificuldade na localização de clientes e aparelhos e armazenamento inadequado de informações pessoais.

Além disso, o sistema possui mecanismos de **autenticação de usuários e proteção de dados**, buscando atender aos requisitos de segurança e às disposições da **Lei Geral de Proteção de Dados (LGPD)**.

---

## 🎯 Objetivo

O principal objetivo do projeto é desenvolver uma aplicação capaz de:

- Cadastrar e gerenciar clientes;
- Cadastrar aparelhos relacionados aos clientes;
- Gerenciar agendamentos de reparos;
- Permitir a edição de informações cadastradas;
- Realizar buscas de clientes;
- Exibir os agendamentos organizados por data;
- Controlar o acesso dos usuários por meio de login;
- Proteger os dados pessoais dos clientes;
- Armazenar o CPF de forma criptografada;
- Facilitar a organização da rotina da assistência técnica.

---

## 🔐 Segurança

O sistema possui recursos destinados à proteção das informações e ao controle de acesso.

Entre os principais mecanismos estão:

- 🔑 **Autenticação de usuários** por meio de login;
- ⏱️ **Controle de expiração da autenticação**;
- ❌ **Validação de falhas no login**;
- 🔒 **Criptografia do CPF dos clientes** no banco de dados;
- 🚪 **Logout do sistema**;
- 🛡️ Controle de acesso às funcionalidades após a autenticação.

A proteção do CPF é especialmente importante devido à natureza pessoal e sensível das informações armazenadas pelo sistema.

---

## ⚙️ Funcionalidades

### 👤 Login

O sistema possui uma tela de autenticação para controlar o acesso dos usuários.

Funcionalidades:

- Login com usuário e senha;
- Validação das informações fornecidas;
- Mensagem de erro em caso de autenticação inválida;
- Controle de tempo da sessão/autenticação;
- Acesso ao sistema somente após autenticação;
- Opção de sair do sistema.

---

### 🏠 Tela Principal

Após realizar o login, o usuário é direcionado para a funcionalidade principal.

A tela apresenta:

- Nome do usuário logado;
- Acesso às demais funcionalidades;
- Opção de gerenciamento de clientes;
- Opção de gerenciamento de aparelhos;
- Opção de gerenciamento de agendamentos;
- Opção de logout.

---

### 👥 Gerenciamento de Clientes

A funcionalidade de clientes permite realizar o gerenciamento dos clientes cadastrados na assistência técnica.

É possível:

- Cadastrar clientes;
- Consultar clientes;
- Pesquisar clientes por um termo;
- Exibir os resultados da busca;
- Editar informações de clientes;
- Salvar alterações no banco de dados.

O CPF dos clientes é armazenado de forma protegida no banco de dados.

---

### 📱 Gerenciamento de Aparelhos

A funcionalidade de aparelhos permite cadastrar os celulares que serão atendidos pela assistência técnica.

Cada aparelho possui informações como:

- Marca;
- Modelo;
- IMEI;
- Defeito relatado;
- Cliente relacionado.

Para cadastrar um aparelho, é necessário associá-lo a um **cliente previamente cadastrado**.

---

### 📅 Gerenciamento de Agendamentos

A funcionalidade de agendamentos permite controlar os reparos que serão realizados pela assistência técnica.

O sistema apresenta:

- Data do agendamento;
- Cliente;
- Aparelho;
- Informações relacionadas ao reparo;
- Listagem dos agendamentos organizada por data.

Também é possível **alterar a data de um agendamento existente**, salvando a alteração no banco de dados.

---

## 🗄️ Banco de Dados

O projeto possui um banco de dados responsável pelo armazenamento das informações do sistema.

As principais entidades utilizadas são:

- **Usuários**
- **Clientes**
- **Aparelhos**
- **Agendamentos**

O banco utiliza **chaves primárias e estrangeiras** para manter o relacionamento entre os registros.

Também foi criado um script SQL para:

- Criar as tabelas;
- Definir os tipos de dados;
- Criar chaves primárias;
- Criar chaves estrangeiras;
- Inserir registros iniciais;
- Manter os relacionamentos entre as entidades.

Cada tabela deve possuir pelo menos **três registros**, conforme as regras definidas para o projeto.

---

## 🔗 Relacionamentos

Os principais relacionamentos do sistema são:

```text
CLIENTE
   │
   ├──────────< APARELHO
   │
   └──────────< AGENDAMENTO
                    │
                    └──── APARELHO
```

Um cliente pode possuir vários aparelhos, enquanto um aparelho pertence a um cliente.

Os agendamentos relacionam o cliente e o aparelho que será atendido.

---

## 📂 Estrutura do Projeto

A estrutura esperada para o projeto é semelhante a:

```text
sistema/
│
├── README.md
├── documentacao.pdf
├── der.png
├── der.pdf
├── assistencia_db.sql
│
└── sistema/
    │
    ├── login/
    │
    ├── principal/
    │
    ├── clientes/
    │
    ├── aparelhos/
    │
    └── agendamentos/
```

A estrutura pode variar de acordo com a implementação utilizada no desenvolvimento.

---

## 📄 Entregas do Projeto

O projeto deve ser entregue em um arquivo compactado (`.zip`, `.rar` ou `.7zip`) contendo os seguintes itens:

| Nº | Entrega | Arquivo/Diretório |
|---:|---|---|
| 1 | Documentação de software | `documentacao.pdf` |
| 2 | Diagrama Entidade-Relacionamento | `der.png` / `der.pdf` |
| 3 | Script de criação e população do banco | `assistencia_db.sql` |
| 4 | Funcionalidade de Login | Diretório `sistema` |
| 5 | Funcionalidade Principal | Diretório `sistema` |
| 6 | Gerenciamento de Clientes | Diretório `sistema` |
| 7 | Gerenciamento de Aparelhos | Diretório `sistema` |
| 8 | Gerenciamento de Agendamentos | Diretório `sistema` |

---

## 📊 Diagrama Entidade-Relacionamento

O projeto também possui um **Diagrama Entidade-Relacionamento (DER)**, utilizado para representar visualmente a estrutura do banco de dados, suas entidades e os relacionamentos existentes entre elas.

O arquivo do diagrama deve ser entregue em formato:

```text
der.png
```

ou

```text
der.pdf
```

---

## 🧪 Regras de Negócio Implementadas

O sistema segue as principais regras estabelecidas para o projeto:

1. Todas as tabelas possuem registros para testes.
2. As chaves primárias e estrangeiras são respeitadas.
3. O login realiza validação de autenticação.
4. O sistema informa quando ocorre uma falha no login.
5. O CPF dos clientes é armazenado de forma criptografada.
6. O sistema identifica o usuário atualmente logado.
7. O usuário pode acessar as funcionalidades disponíveis.
8. O usuário pode sair do sistema.
9. É possível pesquisar clientes.
10. É possível editar os dados dos clientes.
11. As alterações são salvas no banco de dados.
12. Os agendamentos são apresentados por ordem de data.
13. Os dados do cliente e do aparelho são apresentados no agendamento.
14. É possível alterar a data de um agendamento.
15. Todo aparelho cadastrado deve estar relacionado a um cliente existente.

---

## 🚀 Como Executar o Projeto

### 1. Clonar ou copiar o projeto

Coloque os arquivos do projeto em um diretório de sua preferência.

### 2. Configurar o banco de dados

Execute o arquivo:

```text
assistencia_db.sql
```

no sistema gerenciador de banco de dados utilizado pelo projeto.

### 3. Configurar a conexão

Verifique no código-fonte as configurações de conexão com o banco de dados, como:

- Host;
- Porta;
- Usuário;
- Senha;
- Nome do banco de dados.

### 4. Executar o sistema

Após configurar o banco de dados e as dependências necessárias, execute a aplicação utilizando o comando correspondente à tecnologia utilizada no projeto.

---

## 🛠️ Tecnologias Utilizadas

As tecnologias utilizadas podem incluir:

- **HTML5** — estrutura das páginas;
- **CSS3** — estilização da interface;
- **JavaScript** — funcionalidades da aplicação;
- **Banco de dados SQL** — armazenamento das informações;
- **Sistema de autenticação** — controle de acesso;
- **Criptografia** — proteção dos dados pessoais.

---

## 📚 Documentação

A documentação técnica do projeto apresenta informações relacionadas ao funcionamento do sistema, requisitos funcionais, regras de negócio, estrutura do banco de dados e demais informações necessárias para manutenção e evolução da aplicação.

Os arquivos de documentação são:

```text
documentacao.pdf
der.png
der.pdf
assistencia_db.sql
```

---

## 👨‍💻 Projeto Acadêmico

Este projeto foi desenvolvido como atividade acadêmica com o objetivo de aplicar conhecimentos de:

- Desenvolvimento de sistemas;
- Banco de dados;
- Modelagem de dados;
- Autenticação;
- Segurança da informação;
- Criptografia;
- Desenvolvimento de interfaces;
- Requisitos de software;
- Documentação técnica.

---

## 📌 Considerações Finais

O sistema de assistência técnica foi desenvolvido para proporcionar uma forma mais organizada, segura e eficiente de administrar os atendimentos.

A aplicação centraliza informações de **clientes, aparelhos e agendamentos**, reduzindo problemas relacionados ao controle manual e facilitando o acesso às informações necessárias para a realização dos reparos.

A utilização de autenticação, controle de sessão e proteção do CPF também contribui para aumentar a segurança das informações armazenadas no sistema.

---
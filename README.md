# Projeto Chat Bot da FURIA

Este é um projeto de **Chat Bot informativo da FURIA**, voltado para os fãs do time profissional de Counter-Strike 2 masculino. 

> 📌 Este projeto foi desenvolvido como parte de um **desafio técnico** para uma vaga na equipe de tecnologia da **FURIA Esports**.

Com ele, você pode:

- 📆 Visualizar **próximas partidas** e **partidas anteriores**
- 🧑‍🤝‍🧑 Ver **jogadores** e detalhes de cada um (nome, função, posição)
- 📜 Conhecer a **história da FURIA**
- 📧 **Cadastrar seu e-mail** para receber **notificações automáticas** sobre jogos
- 🔄 Obter **dados atualizados em tempo real** via API PandaScore

Você pode acessar o projeto funcionando neste link:  
👉 **[https://furia-chat-bot-front.vercel.app/](https://furia-chat-bot-front.vercel.app/)**

---

## 🚀 Tecnologias Utilizadas

- 🖥️ **Frontend:** Angular
- ⚙️ **Backend:** Spring Boot
- 🗄️ **API Externa:** PandaScore API
- 🐳 **Containerização:** Docker
- ☁️ **Hospedagem Backend:** Render
- 🌐 **Hospedagem Frontend:** Vercel

---

## 🗂️ Estrutura do Projeto
```
furia-chat-bot/
├── backend/                                      # Backend Spring Boot
│   ├── Dockerfile
│   └── src/
│       └── main/
│           ├── java/com/lansy/project/furia_chat_bot/
│           │   ├── client/                       # Cliente para comunicação com a API PandaScore
│           │   ├── configuration/                # Configurações (Beans, Swagger, CORS, etc.)
│           │   ├── controller/                   # Controladores REST
│           │   ├── cors/                         # Políticas CORS
│           │   ├── dto/                          # Data Transfer Objects
│           │   ├── model/                        # Entidades e modelos de domínio
│           │   ├── service/                      # Regras de negócio
│           │   ├── util/                         # Classes utilitárias
│           │   └── FuriaChatBotApplication.java  # Classe principal (ponto de entrada)
│           └── resources/                        # application.yml e demais configs
│
├── frontend/                                     # Frontend Angular
│   ├── Dockerfile
│   └── src/
│       ├── app/
│       │   ├── features/main-page/               # Página principal (componente e layout)
│       │   ├── models/                           # Interfaces e modelos de dados
│       │   ├── services/                         # Serviços (API e lógica de estado)
│       │   ├── app.component.*                   # Componente raiz
│       │   ├── app.config.ts                     # Configurações gerais
│       │   ├── app.config.server.ts              # Configurações do servidor (URLs etc.)
│       │   └── app.routes.ts                     # Rotas da aplicação
│       ├── assets/                               # Recursos estáticos (imagens, ícones, etc.)
│       ├── environments/                         # Configurações de ambiente (prod/dev)
│       ├── index.html                            # HTML base
│       ├── main.ts                               # Ponto de entrada do Angular
│       ├── styles.css                            # Estilização global
│       └── angular.json                          # Configuração do Angular
│

└── README.md                                     # Documentação
```

---

## 📐 Padrões de Projeto Utilizados

### 🔧 Backend (Spring Boot)

- **Camadas Bem Definidas (Controller → Service → DTO/Model):**  
  Organização baseada em responsabilidades, seguindo o padrão MVC.

- **DTO (Data Transfer Object):**  
  Utilizado para estruturar os dados que trafegam entre cliente e servidor, desacoplando das entidades.

- **Service Layer Pattern:**  
  Encapsula a lógica de negócio, mantendo as controllers limpas.

- **HTTP Client (API externa):**  
  Separação clara para chamadas à API PandaScore, garantindo manutenção e testes mais fáceis.

- **Utility Classes:**  
  Agrupamento de funções reutilizáveis e helpers.

- **Configuration Classes:**  
  Classes responsáveis por configurar aspectos do projeto (ex: CORS, beans globais, Swagger etc).

---

### 🌐 Frontend (Angular)

- **Arquitetura Modular e por Features:**  
  Estrutura baseada em domínio (ex: `features/main-page`), facilitando manutenção e escalabilidade.

- **Service Pattern:**  
  Toda a lógica de chamadas HTTP e estados compartilhados é encapsulada em `services`.

- **Modelos Tipados com TypeScript:**  
  Utilização de `interfaces` para tipar dados e prevenir erros de runtime.

- **Environment Configuration:**  
  Separação de configurações para ambientes de desenvolvimento e produção.

- **Routing Centralizado:**  
  Gerenciamento das rotas em um único arquivo (`app.routes.ts`) seguindo boas práticas Angular.



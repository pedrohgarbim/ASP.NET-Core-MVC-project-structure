# 📓 DiaryApp - Estrutura Completa do Projeto ASP.NET Core MVC

Este documento explica a estrutura do projeto **DiaryApp** e detalha a função de cada pasta e arquivo presente. O objetivo é facilitar o entendimento do funcionamento de uma aplicação **ASP.NET Core MVC**.

## 🖥️ O que é ASP.NET Core MVC?

O **ASP.NET Core MVC** é um framework de desenvolvimento web que utiliza o padrão **Model-View-Controller (MVC)**. Esse padrão separa a aplicação em três componentes principais:

- **Model**: Responsável pela lógica de negócios e interação com os dados.
- **View**: Onde a interface de usuário é definida.
- **Controller**: Lida com as requisições do usuário e retorna as respostas apropriadas.

## 📁 Estrutura do Projeto

Aqui está uma explicação de cada pasta e arquivo presente no projeto **DiaryApp**.

### 🌐 wwwroot

A pasta **wwwroot** contém os arquivos estáticos da aplicação. Esses arquivos são diretamente acessados pelos navegadores e incluem:

- **css**: 📄 Aqui ficam os arquivos de estilo CSS que definem a aparência visual da aplicação.
- **js**: ⚙️ Esta pasta contém os arquivos JavaScript que proporcionam interatividade e funcionalidades dinâmicas ao site.
- **lib**: 📚 Bibliotecas externas, como **Bootstrap** e **jQuery**, que ajudam a construir a interface de usuário de maneira rápida e eficiente.
- **favicon.ico**: 🖼️ Arquivo de ícone exibido na aba do navegador ao lado do título da página.

### 🗂️ Controllers

Os **Controllers** são responsáveis por receber as requisições feitas pelos usuários, processar essas requisições, e definir qual **View** será exibida. Eles também interagem com os **Models** para obter ou atualizar dados.

- **Exemplo**: O **HomeController** decide qual página será exibida quando o usuário acessar a URL correspondente.

### 📑 Models

Os **Models** representam os dados da aplicação e são responsáveis pela lógica de negócios. No contexto de um aplicativo de diário, um **Model** poderia ser uma classe que define uma entrada de diário, contendo propriedades como **Título**, **Conteúdo**, e **Data**.

### 👁️ Views

As **Views** são responsáveis por exibir os dados ao usuário. Elas utilizam a linguagem **Razor** (arquivos **.cshtml**) para renderizar HTML dinâmico. Em nosso projeto, elas podem incluir formulários para adicionar, editar ou visualizar entradas no diário.

- **Shared**: 📋 Contém partes de código que são compartilhadas entre várias views, como o layout ou os menus de navegação.
  - **_ViewImports.cshtml**: 🚀 Arquivo que permite importar namespaces ou configurar o comportamento das Views de maneira global.
  - **_ViewStart.cshtml**: 🔧 Define o layout padrão a ser utilizado em todas as views.

### ⚙️ Arquivos de Configuração

#### **appsettings.json**
O arquivo `appsettings.json` contém configurações que podem ser usadas em toda a aplicação, como strings de conexão com banco de dados ou outras configurações essenciais para a execução.

#### **appsettings.Development.json**
Este arquivo é uma versão específica para o ambiente de desenvolvimento. Ele pode conter configurações sensíveis ou específicas para quando a aplicação estiver rodando localmente.

#### **launchSettings.json**
Esse arquivo define como a aplicação será executada em diferentes ambientes, como **IIS Express** ou **Kestrel**. Ele permite configurar portas, variáveis de ambiente, e muito mais.

### 🏁 Program.cs
![image](https://github.com/user-attachments/assets/4a196324-cd46-4e1e-aea2-cfb5286b5d62)


O arquivo **Program.cs** é o ponto de entrada da aplicação. Ele define o host da aplicação e contém a lógica para inicializar o servidor, dependenciasm, configurar middlewares e serviços essenciais.
## ⚙️ Middleware 

O **middleware** é a parte essencial que processa cada requisição na aplicação. Ele permite adicionar lógica de segurança, roteamento e mais. É uma série de componentes (ou funções) que processam as requisições HTTP no pipeline da aplicação. Cada middleware pode fazer algo com a requisição e decidir se deve passar para o próximo componente, Basicamente Middleware diz em que ordem as coisas devem ser executadas.

- `app.UseHttpsRedirection()`: Redireciona requisições HTTP para HTTPS para segurança 🔐.
- `app.UseRouting()`: Habilita o sistema de roteamento de URLs 🗺️.
- `app.UseAuthorization()`: Checa as permissões do usuário para acessar recursos 🔒.
- `app.UseHsts()`: Habilita a segurança HSTS para garantir que sempre usamos HTTPS 📡.

## 🌟 Services 

Os **services** são responsáveis por adicionar funcionalidades reutilizáveis, como a adição de **controllers com views**. São objetos que fornecem funcionalidades reutilizáveis na aplicação. Eles são configurados em um container de injeção de dependência e podem ser injetados em várias partes da aplicação. Aqui, usamos:

- `builder.Services.AddControllersWithViews()`: Habilita o uso de **controllers** e **views** para renderizar HTML dinâmico.

## 🗺️ Routing 

O **routing** define como as URLs são mapeadas para as ações dos controladores. É o mecanismo que mapeia as requisições HTTP para controladores e ações específicos com base na URL. A rota padrão configurada é:

- `{controller=Home}/{action=Index}/{id?}`: Roteia para o controlador `Home` e a ação `Index`, com um parâmetro opcional `id`.

---

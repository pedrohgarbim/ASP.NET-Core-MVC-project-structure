# 📓 DiaryApp - Um Aplicativo de Diário com ASP.NET Core MVC
## 🖥️ O que é ASP.NET Core MVC?

O **ASP.NET Core MVC** é um framework para a criação de aplicações web. Ele segue o padrão **Model-View-Controller (MVC)**, que separa a lógica da aplicação em três partes principais:
1. **Model** - Regras de negócios e interação com o banco de dados.
2. **View** - Interface do usuário.
3. **Controller** - Coordena a interação entre as **Views** e os **Models**.

## 📁 Estrutura do Projeto

A estrutura do projeto segue a organização padrão de uma aplicação **ASP.NET Core MVC**, onde cada parte desempenha um papel importante.

### 1. 🛠️ launchSettings.json
Este arquivo contém as configurações de execução da aplicação. Ele especifica como o projeto será iniciado em diferentes ambientes, como **IIS Express** ou **Kestrel**. Aqui você pode definir parâmetros como a **porta** em que a aplicação será executada localmente, e configurações de ambiente de desenvolvimento.

### 2. 🔗 Connected Services
Nesta seção, você pode conectar serviços externos ao projeto, como serviços em nuvem ou APIs de terceiros. Esses serviços facilitam a comunicação com outros sistemas.

### 3. 📦 Dependencies
Aqui é onde você encontra todas as **dependências** que o projeto utiliza, como pacotes NuGet e bibliotecas necessárias para a aplicação funcionar corretamente. Por exemplo, pacotes para interação com banco de dados, segurança e autenticação.

### 4. 🌐 wwwroot
Esta pasta armazena os arquivos estáticos da sua aplicação, como **CSS**, **JavaScript** e **imagens**. Tudo o que é necessário para a aparência e interatividade do frontend da aplicação.

### 5. 🗂️ Controllers
Os **Controllers** são responsáveis por lidar com as requisições do usuário e definir as respostas a serem enviadas de volta. Em um projeto MVC, os controllers são o coração da lógica de controle. Eles determinam o que acontece quando o usuário faz uma requisição para uma URL específica.

**Exemplo:**  
Se o usuário solicitar `https://localhost:5001/home/index`, o **HomeController** irá decidir qual view (página) será exibida e qual model será usado.

### 6. 📑 Models
Os **Models** são classes que representam os dados da aplicação. Eles são responsáveis por definir como os dados serão armazenados, validados e manipulados. Em uma aplicação de diário, o **Model** poderia incluir uma classe **DiaryEntry**, que tem propriedades como **Data**, **Título**, e **Conteúdo**.

### 7. 👁️ Views
As **Views** são responsáveis pela exibição dos dados ao usuário. Elas definem como o conteúdo será apresentado na interface da aplicação. No **DiaryApp**, as views renderizam as entradas do diário, formulários de adição e edição de registros.

### 8. 🔄 Operações CRUD
O **DiaryApp** implementa as operações **CRUD** (Create, Read, Update, Delete) básicas. Estas operações permitem ao usuário:
- **Criar** uma nova entrada no diário 📝
- **Ler** as entradas do diário 📖
- **Atualizar** ou editar entradas existentes ✍️
- **Excluir** uma entrada do diário 🗑️

Essas operações são controladas por **Controllers** que interagem com os **Models** e enviam as atualizações para as **Views**.

### 9. 🏁 Program.cs
O arquivo `Program.cs` é o ponto de entrada da aplicação. Ele contém a lógica que inicia o **host** da aplicação e configura o ambiente de execução. Esse arquivo define como a aplicação será inicializada, configurando o servidor web, serviços necessários e outras configurações importantes.

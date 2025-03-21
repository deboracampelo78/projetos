# Setup do Ambiente

### Passo a Passo

1. **Remover o Node.js v10.24.1**  
    Certifique-se de desinstalar a versão antiga do Node.js.

2. **Instalar o NVM-Windows**  
    Baixe e instale o [NVM-Windows](https://github.com/coreybutler/nvm-windows). Durante a instalação, clique em "Next" em todas as etapas.

3. **Habilitar o controle de NPM/Node pelo NVM**  
    Execute o comando:  
    ```bash
    nvm on
    ```

4. **Instalar a versão 10.24.1 do Node.js**  
    Abra o PowerShell e execute:  
    ```bash
    nvm install 10.24.1
    ```

5. **Instalar a versão mínima necessária para a POC (18.19.0)**  
    Execute:  
    ```bash
    nvm install 18.19.0
    ```

6. **Habilitar a versão desejada do Node.js**  
    Para usar a versão 18.19.0, execute:  
    ```bash
    nvm use 18.19.0
    ```

7. **Instalar o Yarn**  
    Instale o Yarn globalmente com o comando:  
    ```bash
    npm i -g yarn
    ```

8. **Instalar as dependências do projeto**  
    Na raiz do diretório do projeto, execute:  
    ```bash
    yarn
    ```

9. **Executar o projeto**  
    Inicie o projeto com o comando:  
    ```bash
    yarn dev
    ```

---

## Componentes

Explore os componentes disponíveis no projeto:

- **[Processes](src/app/components/Processes/README.md)**  
  Documentação do componente `Processes`.

- **[SideBarMenu](src/app/components/SidebarMenu/README.md)**  
  Documentação do componente `SideBarMenu`.

- **[Tabs](src/app/components/Tabs/README.md)**  
  Documentação do componente `Tabs`.

- **[ConfigLoader](src/app/components/ConfigLoader/README.md)**  
  Documentação do componente `ConfigLoader`.

- **[CustomModal](src/app/components/CustomModal/README.md)**  
  Documentação do componente `CustomModal`.

- **[Message](src/app/components/ErrorsAlertsInfo/README.md)**  
  Documentação do componente `Message`.

---

## Code Review

Confira processos e boas práticas para um code review completo no [Guia do Code Review](/GuiaCodeReview.md).

---

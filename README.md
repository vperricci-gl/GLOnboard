# Bem-vindo à Grouplink!

Aqui você encontrará como configurar o seu ambiente de desenvolvimento.

## Configuração do Ambiente

1. **Instalar o Node.js**: Certifique-se de que o Node.js está instalado em sua máquina. Você pode baixá-lo em [nodejs.org](https://nodejs.org/).

2. **Instalar o Git**: O Git é necessário para clonar o repositório. Você pode baixá-lo em [git-scm.com](https://git-scm.com/).

3. **Configurar uma chave ssh**: Se você ainda não possui uma chave SSH configurada, siga as instruções em [Documentação do GitHub](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

4. **Adicionar a chave SSH ao GitHub**: Após gerar a chave SSH, adicione-a à sua conta do GitHub seguindo as instruções em [Adicionando uma nova chave SSH à sua conta do GitHub](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

5. **Configurar um token para o .npmrc no GitHub**: Para acessar os pacotes privados do GitHub, você precisará configurar um token de acesso pessoal. Siga as instruções em [Criando um token de acesso pessoal](https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

   Após criar o token, adicione-o ao seu arquivo `.npmrc` na raiz do projeto:

   ```bash
   //npm.pkg.github.com/:_authToken=SEU_TOKEN_AQUI
   @group-link-one:registry=https://npm.pkg.github.com
   ```

## Clonando e Configurando o Projeto

Agora que você já configurou o ambiente, siga os passos abaixo para clonar o repositório e instalar as dependências:

### Instalando o Yalc

Usamos o yalc como gerenciador de pacotes, então certifique-se de que ele está instalado. Você pode instalá-lo globalmente com o seguinte comando:

```bash
npm install -g yalc
```

Ele é usado para gerenciar pacotes locais e facilitar o desenvolvimento, pois temos vários pacotes que são utilizados em conjunto.

### Clonando o Repositório com SSH

```bash
git clone git@github.com:Group-Link-One/Dashboard-Utilities.git
```

### Navegando até o Diretório do Projeto

```bash
cd Dashboard-Utilities
```

### Instalando as Dependências

```bash
npm install
```

> **Nota**: Os arquivos `.env` são fornecidos pela equipe de desenvolvimento. Certifique-se de que você tem acesso a eles. Se não tiver, entre em contato com a equipe para obter os arquivos necessários.

## Regras para o Desenvolvimento

### Conectando o Yalc

Provavelmente sua tarefa envolverá um pacote que já está sendo utilizado no projeto, então você precisará conectar o yalc para que as alterações sejam refletidas no projeto.

**Projetos que podem ser conectados:**

- gl-components
- GLUtils-Web

### 1º Passo: Linkando Pacotes

Você precisará executar o seguinte comando no projeto onde você quer conectar os pacotes (ex: Dashboard-Utilities):

```bash
npm run link
```

Você verá uma mensagem mostrando qual pacote deseja conectar, escolha o pacote desejado e pressione Enter.

### 2º Passo: Publicando Pacotes na Store do Yalc

Nos projetos que podem ser conectados, existe um comando para publicar os pacotes na store do yalc. Execute o seguinte comando no projeto onde você quer publicar os pacotes (ex: gl-components):

```bash
npm run dbw
```

Isso irá ativar o watch do nodemon, onde ele irá monitorar as alterações no código e publicar as alterações na store do yalc após o build.

## Pronto!

Agora você pode começar a desenvolver e testar suas alterações localmente. 🚀

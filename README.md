# Criando um pacote com github pages

1. Criar um repositório no github seguindo o procedimento padrão.

   1.1 A pasta obrigatoriamente tem que ser um repositório válido do GitHub.

   1.2 O comando npm init deverá ser executado apenas quando o repositório estiver devidamente
   configurado, pois é necessário que o package.json contenha as informações do repositório

2. Criar em novo token de acesso do github.

   2.1 Clique na sua foto de perfil no canto superior esquerdo.

   2.2 Clique em **settings**.

   2.3 Clique em **developer settings** no canto esquerdo.

   2.4 Clique em **Personal access tokens**.

   2.5 Clique em **Generate new token** e adicione um nome para o token.

   2.6 Adicione as permissões necessárias (as permissões **repo** e **read:packages** são
   obrigatórias para a criação do pacote) e clique em **Generate token.**

   2.7 Depois de criado, copie o token e guarde em algum lugar seguro pois ele não ficará visivel
   depois que você sair da página.

3. Execute o comando `npm login --registry=https://npm.pkg.github.com` no terminal.

   3.1 Quando solicitado, insira seu nome de usuário e email público do github,
   quando a senha for solicitada cole o seu token de acesso.

4. Insira no package.json a propriedade:

   `"publishConfig": { "registry": "https://npm.pkg.github.com/@NOME_ORGANIZACAO" }`

5. Depois disso você está pronto para criar seus códigos do projeto

6. Execute `npm publish` para publicar o pacote no Github Packages

# Instalando o pacote

1. Crie um arquivo .npmrc na raíz do projeto

2. Insira a linha `@NOME_ORGANIZACAO:registry=https://npm.pkg.github.com`

3. O comando correto para a instalação do pacote estará dentro da aba **Packages**
   na página da organização no GitHub, será algo parecido com `npm install @NOME_ORGANIZACAO/NOME_PACOTE@1.0.0`

OBS: O usuário logado com o comando `npm login` nas instruções do tópico
anterior deve ser um usuário válido que seja membro da organização

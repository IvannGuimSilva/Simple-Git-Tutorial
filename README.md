![git_imag_illustration](https://raw.githubusercontent.com/IvannGuimSilva/Simple-Git-Tutorial/master/images/unsplash_git_img.jpg)

# Tutorial de comandos Git
**`nota:`** ` eu posso ter feito alguns testes de comandos para aprendizado aqui dentro.`

Esse arquivo tem como objetivo reforçar, ensinar e clarear na minha mente 
alguns conceitos de versionamento de código.

## Apresentação dos Conceitos:

Estou usando guias de git muito bons em inglês que ensinam
toda a metodologia e conceito de git, vindos do tutorial no site dev.to [aqui.](https://dev.to/gothamv/learn-the-basics-of-git-in-under-10-minutes-475c)

Todos os comandos aqui listados serão apresentados com
técnicas de formatação(*markdown*) vindas do próprio 
[Github Guides!](https://guides.github.com/features/mastering-markdown/) Um tipo de ferramenta que é muito valiosa para versionamento também.

## Primeiros passos e lista de comandos:

#### 0. Faça download do GIT (caso não tenha)

Você precisará desse programa, pois ele é justamente o programa controlador de versão. Caso você use windows, vá até esse [link](https://git-scm.com/download/win) para download **`instantâneo`** do mesmo.

Verifique no seu prompt de comando, com o comando **git --version** se o git foi instalado. Caso afirmativo, aparecerá o número da versão, caso contrário o windows simplesmente avisará que não há nenhum comando dessa natureza registrado.

#### 1. Crie um repositório no Github

Crie um repositório vazio no github para futuramente usá-lo para sincronizar um diretório dentro do seu computador a ele, e assim fazer seu esquema de controle de versão linkado ao seu github. 

#### 2. Torne um diretório do seu computador num diretório GIT 

#### `AVISO:`
#### `O principal começa aqui.`

Vá dentro da pasta ao qual você deseja transformar no seu repositório local dentro do seu PC. Por meio do cmd (prompt de comando); vá dentro dela, usando o comando **cd nome_da_pasta** e digite o comando **git init** dentro dela.

Isso fará com que seu PC reconheça essa pasta como um repositório local GIT.

#### 3. **Identifique-se como usuário GIT**


Diga ao sistema de versionamento quem você é, isso é vital para todo o histórico de mudança de arquivos, pois informa quem é o responsável pelas tais mudanças. Recomendo usar seu nome do Github e o seu email do Github também.

Para fazer isso, digite dentro do prompt:

<div>
  <strong>git config --global user.name</strong> "seu nome do github"
</div>
<div> 
  <strong>git config --global user.email</strong> "seu email do github"
</div>
<div> 
  <strong>git config --global --list</strong> | Mostrará as informações que você digitou.
</div>



#### 4. **git add**

Agora que você finalmente inicializou sua pasta como um repositório local dentro do seu PC, e já existe um repositório no Github esperando para se conectar  com este seu projeto aqui na sua máquina. Nós já podemos fazer algo.

De maneira normal, você pode criar, editar e excluir arquivos aqui dentro da sua pasta. Mas eles não estarão sendo rastreados de imediato pelo sistema de versionamento. Isso significa que qualquer alteração neles será tratada como qualquer outra em alguma pasta aleatória do seu computador.

Para ativar essa funcionalidade é necessário um dos seguintes comandos:

- Variações:
  - **git add** *nome_arquivo_escolhido*
    - Adiciona o arquivo escolhido dentro do seu diretório git, à lista de espera (ou lista de arquivos rastreados / *git staged files*) para serem **commitados futuramente** (resumindo, agora o sistema está de olho neles 👀). E sempre que você mudar alguma coisa neles, ou apagá-los, isso será registrado.

  - **git add .**
    - Adiciona todos os arquivos e pastas dentro do seu diretório git a lista de espera para serem commitados. Também conhecida como *git staged files waiting for commit*.
  - **git restore --staged** nome_arquivo
    - Caso você não queira mais que o seu arquivo escolhido seja rastreado e esteja na lista de espera, digite isso e ele voltará a ser só um arquivo comum.
  - **git restore arquivo_escolhido**
    - Esse vai mais longe, ele serve caso você queira desfazer mudanças em arquivos que nem estão marcados como *staged files*.
  - **git restore .**
    - É a mesma coisa que o de cima, porém para todos os arquivos do seu diretório.

#### 5. **git status**

Digitando apenas **git status** dentro da sua pasta linkada ao git, você consegue saber quais arquivos estão sendo observados / em espera para poderem ser **commitados**. Ou novamente, como diz o termo técnico: "*git staged files*".

Caso você ainda não tenha adicionado nenhum, eles aparecerão como não adicionados em vermelho. Agora, depois de vc dar **git add**, esses arquivos aparecerão em uma lista simples em verde, esperando que você finalmente dê um commit (**que você ainda não deu, claro**) e *finalmente os registre como um novo degral no grupo de mudanças importantes do seu projeto* 😊.

#### 6. **git commit**

Agora finalmente chegamos nele! **git commit**!!! <h4>"Ele é o responsável por pegar toda aquela lista de arquivos sendo rastreados e registra-los oficialmente como uma mudança dentro da linha do tempo de desenvolvimento do seu projeto."</h4>

#### `Imagine comigo:`

Imaginando que eu criei, pus para rastrear mudanças (**git add**) e modifiquei 1 arquivo.html mais 2 arquivos.css dentro do meu projeto. Quando eu desse **git commit** após ter feito tudo isso, eu registraria todos esses passos importantes, e ainda adicionaria uma descrição para falar o quê eu fiz. No meu caso, eu pessoalmente escreveria:

#### `"Criação e modificação inicial de html e estilos."`

Ou na forma de comando:

#### `git commit -m "Criação e modificação inicial de html e estilos."`

Como pode imaginar **-m** vem de *message* ou mensagem.

Ou seja, a grande idéia é que cada **commit** representa um **bloco de mudanças marcantes que eu fiz em um determinado momento**.

- Variações:
  - **git commit -m** "título descritivo"
    - Quando você faz um **commit**, é **obrigatório** que você ponha um título descrevendo o quê você fez. Pois o grande propósito da coisa é justamente que outras pessoas que venham a ver seu código e que trabalham com você entendam o quê você fez e os seus motivos para isso naquele momento.
  - **git commit -m** "título" **-m** "parágrafo descritivo"
    - Esse é exatamente igual ao anterior só que dá a você alternativa a mais de ir um pouco além na descrição, porém é um pouco desconfortável pois o prompt de comando não permite quebra de linhas e fica difícil de escrever algo muito grande. 
  - **git commit**
    - #### `AVISO:`
    - ##### `Não é possível usar esse comando sem algumas exigências.`
    - Honestamente, esse daqui é o melhor comando de todos (ao menos para mim 😅) pois ele permite que quando eu der **commit**, meus commits tenham tanto títulos descentes do que eu mudei, quanto parágrafos bem definidos caso a mudança nos meus arquivos tenha sido muito grande ou complexa.
    - **Porém de imediato o prompt de comando não reconhece ele, e dará erro caso você só escreva git commit agora**. Para que o prompt do windows aceite essa variação, escreva no seu prompt a seguinte instrução:
    - #### ` git config --global core.editor "code --wait" `
    - Isso fará com que o VScode seja reconhecido como a ferramenta que te ajudará a escrever melhores descrições. 
    - **Finalmente**, assim que eu escrevo o comando **git commit**, o prompt ligará o VScode automaticamente, e me mostrará uma janela para eu poder escrever tanto o título do meu commit quanto o parágrafo descritivo. Se eu quiser, só o título mesmo.
    - Quando essa tela do VScode aparecer, ela terá textos escritos com hashtag (**#**) antes deles e eles não devem ser apagados. O quê você deve fazer é simplesmente escrever debaixo desses textos o seu título. Caso você quiser um parágrafo descritivo também, para fazer isso só dê um enter, pule uma linha e escreva-o.
    - Depois de escrever o quê você queria, salve-o pelo próprio VScode (**File > Save** ou **Ctrl + S**) e feche-o. Assim o prompt de comando que você havia deixado aberto para fazer isso que eu falei; exibirá a mensagem de que o seu **commit** foi devidamente registrado 😁😁.


#### 7. **git reset HEAD~1**
Esse comando é bem simples conceitualmente falando. Ele simplesmente desfaz o último **commit** feito por você. E sim, ele é case sensitive, logo escreva direitinho.

#### 8. **git remote**
Estamos chegando naquele momento onde finalmente iremos conectar seu projeto / repositório local no o seu repositório remoto lá no Github. E para fazermos essa ponte, obviamente você deve avisar ao seu git para onde você enviará todas essas informações. 

Para fazer isso use o comando:

#### `AVISO:`
#### `Versão principal do comando:`

- **git remote add** "apelido_repositorio_github" "url_repositorio_github"
- ##### Exemplo abaixo:
- **git remote add** `origin` https://github.com/nomeUsuario/SeuRepositorioGithub.git
- Deixando bem claro, **origin é o apelido que o seu repositório local dará ao seu repositório remoto, aquele que fica lá no seu github**.
- Levando em conta que o git é uma linha do tempo que pode levar a várias versões alternativas; imagine que tudo isso é um grande árvore, a raiz é o início do universo e o tronco é a timeline principal. Além da linha do tempo principal, existem suas versões alternativas, que seriam galhos ou **branches** diferentes da nossa árvore. Você pode escolher em qual galho / timeline quer por suas atualizações, caso não queria ter o risco de comprometer o branch principal com algum erro, ponha em um alternativo (ainda mais se for um projeto da sua empresa, porque você pode ser demitido 😙).
- Escreva esse comando para adicionar um novo repositório remoto do github ao qual seu projeto será conectado e futuramente lançado (e sim, eu disse um novo pois dá pra conectar seu repositório local em mais de um repositório remoto). Mas isso só fez a ponte, então calma, porque seu projeto ainda está na sua máquina.

#### `outras variações:`

- **git remote -v**
  - Mostrará todos as urls de repositórios remotos no github ao qual o seu repositório local tem conexão, junto dos respectivos apelidos deles.
- **git remote rm** apelido_repositorio_remoto
  - Remove a conexão com algum repositório remoto do github. Por exemplo; se eu não quisesse que meu projeto tivesse mais ligação com aquele repositório do meu github, ao qual eu apelidei de **origin**; eu simplesmente digitaria no meu prompt:
  - **git remote rm** origin
    - Isso simplesmente apagaria minha conexão com ele. Caso eu quisesse me conectar novamente; escreveria **git remote add** *apelido* de novo, e se eu quisesse poderia por até um outro apelido com esse mesmo comando, já que é ele que determina qual será a url da sua conexão, e de que você a apelidará.

#### 9. **git push**
Agora finalmente, iremos mandar os arquivos do seu repositório local até o seu repositório remoto 😁😁😁. Sendo bem direto, existem variacões desse comando (como tudo em git), bem, ai está finalmente o quê você usará para mandar seus arquivos ao seu repositório remoto:

  - **git push** **`apelido_repositorio_remoto`** **`nome_branch_do_repositorio_remoto_que_vc_deseja`**
    - Exemplo:
    - **git push** **`origin`** **`master`**
    - O quê acontece aqui, é que você está *empurrando* / *pushing* seus dados do seu branch local (**que por padrão se chama master também**) até o repositório escolhido por você (que já possui um apelido dado pelo seu git, que aqui foi apelidado de **origin**).
    - E depois de todos esses detalhes, você **FINALMENTE** enviou seus dados até o seu Github! É isso ai 🤘.

#### 10. git diff
Um comando muito simples e bacana, caso você tenha arquivos que não foram nem rastreados pelo git (ou seja, você nem deu **git add** neles e eles são meros arquivos *normais* no seu diretório git), você pode usar esse comando para ver literalmente as diferenças que você pos neles; sejam elas, mudanças apenas no texto deles mesmo. Apenas escreva seu **git diff**.

#### 11. git log
Esse aqui é um comando muito útil, caso você queira ver todos os **commits** que você fez; digite simplesmente **git log**. Mostrando dados como; nome do branch local no qual você fez seu **commit**, para onde você os mandou (se os mandou para algum repositório remoto), data do **commit**, email do autor (email que você botou) e etc.

Caso você tenha feito muitos commits, nem todos aparecerão, devido aos próprios limites de tamanho físico da tela, caso você queira que eles fiquem aparecendo na sua tela **igual a um terminal do linux**, apenas digite tecla para baixo ⬇️, e eles simplesmente irão aparecer deslizando. Caso não esteja interessado nisso, simplesmente aparte **w + q** igual no linux de novo, e pronto, a lista some.

#### 12. git branch --show-current
Mostra o **branch atual** que você está usando no seu repositório local do seu PC. Exemplos: **main** ou **principal**, branch_de_testes, versão_do_projeto_bugada etc.

#### 13. git branch
Mostra todos os branches que o seu repositório local possui. Se você só tiver um e tiver acabado de criar seu repositório / projeto local, aparecerá "master" por padrão em verde.

#### 14. git checkout
Esse comando reverte o estado dos seus arquivos para como eles estavam na sua última commitada.
  - Variações:
    - **git checkout .**
      - Reverte todos os seus arquivos no seu repositório para o status deles no commit anterior.
    - **git checkout arquivo_escolhido**
      - Reverterá apenas o status dessse arquivo para como ele era no commit anterior.



#### 15. Racíocinio base para projetos no Github
- `#0` **[sua pasta]** `<= Tenha seu diretório em mãos.`
- `#1` **git init** `<= transforme seu giretório em um giretório git. =D`
- `#2` **git add .** `<= adicione todos os seus arquivos à area de espera.`
- `#3` **git commit -m "Projeto criado"** `<= Faça o seu registro de modificação.`
- `#4` **git push origin master** `<= Mande o que deseja para seu repositório no galho principal.`

#### 16. git clone 

**`Fazendo Download de repositórios`**

Para fazer download de um repositório desejado por você (seja ele seu mesmo ou criado por outra pessoa), apenas use o seguinte comando para clonar esse repositório em sua máquina:

- **git clone URL_repositório_remoto**
  - Exemplo:
    - **git clone** [https://github.com/Gothamv/MuskCult](https://github.com/Gothamv/MuskCult)
    - Fazendo isso você simplesmente vai baixar a versão original à qual eu me inspirei para fazer esse artigo de estudos.

#### 17. git pull

Esse comando traz dados de um branch em um repositório remoto desejado por você lá no github; ao seu repositório local (sendo atualmente usado por você) ai na sua máquina. Juntando os dois e adicionando as novidades (ou concertos) feitos em B para  o seu A.

Ou seja, ele é justamente usado quando você quer trazer as atualizações de um repositório externo para o seu próprio. Por isso a palavra *pull*, pois vem de puxar.

- **git pull** `nome_repositorio_desejado` `branch_desse_repo_desejado`
  - Exemplo:
    - **git pull** origin master
    - Puxa dados vindos do repositório escolhido por você e apelidado de origin, pegando esses dados do branch *master* dele.

Ele é muito útil também quando o repositório do seu github está mais atualizado que o seu local em commits feitos. 

#### 18. git fetch

Este é um primo do nosso anterior, **git pull**. No caso, a palavra *fetch* vem de buscar ou procurar em inglês, e é justamente o quê esse comando faz. Esse comando faz download dos últimos commits feitos no branch remoto, mas *não os incorpora* no repositório local que você está usando. Esses commits só estarão disponíveis no branch **origin \ master**. E o seu branch local atualmente sendo usado (por padrão chamado de master também) continuará intacto em termos de modificações feitas, porém estará em dia com os registros do outro. 

#### 19. git branch nome_do_branch
Muito simples, esse comando cria um novo branch no seu repositório com o nome que você escreveu.
- Exemplos:
  - **git branch** `atualizacao_do_css`
  - Aqui eu simplesmente criei um novo branch que teoricamente vai conter versões atualizadas do CSS do projeto ao qual eu estaria fazendo originalmente.

#### 20. git checkout branch_escolhido
Também é simples, esse comando põe você no branch ao qual você escolheu (**Ele troca você de branch, desde que o branch exista**). Se você estivesse no branch `master` e quissese mudar para o branch chamado `atualizacao_do_css`, você simplesmente escreveria:

- **git checkout** `atualicacao_do_css`

#### 21. Criando um novo branch a partir de um branch escolhido:

Caso você queira criar um **branch B** com as características / commits de um **branch A** já existente, certifique-se que já está dentro do A; caso não esteja, digite **git checkout** `nome_branch_A` para ir para dentro dele. Depois digite **git branch** `nome_branch_B` para criar o branch B baseado nesse branch A. Logo depois dê um **git checkout** `nome_branch_B` para entrar dentro dele.

Esses capítulos são complementos para as partes 12, 13 e 14 desse repositório.

#### 22. git branch -d <branch_local>

Exclui um branch local, mas não fará isso caso esse branch não tenha sigo mesclado (feito *merge*) com o branch master.

#### 23. git branch -D <branch_local> 

Exclui um branch local independente de *merge* ou não.

## Leitura Adicional / Additional Reading

- [Git Commands Tutorial](https://github.com/IvannGuimSilva/Simple-Git-Tutorial/blob/master/README.eng_US.md)

- [How to use git merge in the correct way](https://dev.to/neshaz/how-to-use-git-merge-the-correctway-25pd)

- [Creating a pull request](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)

- [Tutorial simples de pull request](https://github.com/IvannGuimSilva/Teste-Pull-Request)

- [Deleting a local and a remote branch](https://www.freecodecamp.org/news/how-to-delete-a-git-branch-both-locally-and-remotely/)

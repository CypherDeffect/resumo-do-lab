# resumo-do-lab
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO.

## AULA 1.1 - COMPUTAÇÃO EM NUVEM
Valor dos recursos dependem do país

Computação em Nuvem: é o fornecimento de serviços de computação pela internet, habilitando inovações mais rápidas, recursos flexíveis e economias de escala.
Nuvem Privada: 100% on-premise. Serve somente a minha empresa (datacenter próprio). A organização é responsável por operar os serviços. Não fornece acesso a usuários fora da organização.

Nuvem pública: Pertence a serviços de nuvem ou provedor de hosting. Entregam serviços para quem pagar por eles. Acessado via internet, por uma conexão segura. 

Nuvem Híbrida: O melhor dos dois mundos. Modelo multi-cloud: A empresa usa recursos em provedores diferentes, tal como na Azure e na AWS, além de poder manter recursos on-premise.

## AULA 1.2 - COMPARAÇÃO MODELOS DE NUVEM

Nuvem Pública: 
Nenhuma despesa de capital para escalar verticalmente: Você não irá pagar na hora que criar o recurso, mas sim após 30 dias de uso. Isso implica em um custo variável, que irá depender de quanto tempo o recurso ficou em uso, qual a região, etc. (CapEx)

Os aplicativos podem ser provisionados e se provisionados rapidamente.
As organizações pagam apenas pelo o que utilizam. (pay as you go)

Nuvem Privada:
	
As organizações têm controle total sobre os recursos e a segurança;
As organizações são responsáveis pela manutenção e pelas atualizações de hardware. 

Nuvem Híbrida:

As organizações determinam onde executar seus aplicativos;
As organizações controlam a segurança, a conformidade e os requisitos legais;
Fornece maior flexibilidade.


## AULA 1.3 - COMPARAÇÃO ENTRE CAPEX E OPEX
CapEx:  
O gasto inicial de dinheiro em infraestrutura física;
As despesas do CapEx têm um valor que se reduz com o tempo
Compra e configuração de servidores, cabeamento.  
O gasto inicial será muito alto, para a aquisição de novas máquinas, rack, cabeamento, discos, mão de obra e afins. Mas depois de pronto, o custo irá diminuir drasticamente, pois passará a ser apenas de energia, manutenção e mão de obra especializada. 
OpEx:  
Cobrança conforme o uso, porém sempre pagando. (Assim funciona a Cloud)
Gastar com produtos e serviços conforme é necessário, pagamento conforme o uso.
Tudo o que está ativo está sujeito a cobrança

## AULA 2.1.1 - O que é versionamento de código
A cada alteração no seu código, irá gerar uma nova versão. 
Sistemas de Controle de Versão: 
Registra histórico de atualizações de um arquivo;
Gerência alterações
Controle e segurança; 
VCS = Version Control System
Centralizado (CVCS) = CVS, Subversion 
 Apenas um servidor contendo as versões 

Distribuído (DVCS) = Git, Mercurial
Cada versão é duplicado em locais diferentes.
Cada clone é um bkp
possibilita fluxo de trabalho flexível, Pode trabalhar offline

## AULA 2.1.3 - GitHub
Criado em 2008
Comprado pela Microsoft em 2018

## AULA 2.1.3 - Git
git config --global user.name "user"
git config --global user.email "email"
git config --global init.defaultBranch main


## AULA 2.1.4 - Git Autenticando via Token
O GitHub não aceita mais a autenticação por usuário/senha
Gerar Token  em Settings > Developer Settings

git config –global credential.helper store
ai da um git clone https://repositorio.git
Insere usuário e o Token

## AULA 2.1.5 - Git Autenticando SSH Key
Settings > SSH
Em caso de dúvida, seguir a documentação disponível

## AULA 2.2.1 - Criando e Clonando

https://readme.so/pt/editor
git log 
O Git não reconhece diretórios vazios 
	OBS: por convenção, pode ser criado um arquivo chamado “.gitkeep” dentro de um diretório vazio, para que o git o reconheça
echo “nome arquivo ou pasta > .gitignore

Restaurar arquivo:
Caso tenha alterado ou apagado um arquivo e deseja restaurar/voltar, use o comando: 
git restore <nome do arquivo>

Modificar mensagem do commit que feito
git commit –amend -m “nova mensagem”
git commit –amend (sem o -m, irá abrir o editor de texto)


Resetar commit
git reset –soft <hash do commit>
Dessa maneira, os arquivos que foram comitados anteriormente voltam para a área de preparação.

git reset –mixed <hash do commit>
Os arquivo commitados voltam para ao estado “untracked”, ou seja, antes de serem adicionados 

git reset –hard <hash do commit>
Irá desfazer o commit e apagar os arquivos do diretório

Verificar o histórico:
git reflog


## AULA 2.2.1 - Enviando e baixando alterações com repo remoto
git remote add origin url

Verificar branch atual com : git branch
Se precisar alterar, use git branch -M main

Abrir o editor web do github. Com o repositório aberto, aperte a tecla ponto “. “


## AULA 2.2.1 - Trabalhando com Branches
O último commit sempre fica atrelado a branch no qual foi feito

Criar nova branch e mudar para ela
git checkout -b <nome branch>

Mudar para outra branch
git checkout <nome branch>

Mesclar conteúdo das branch

git merge <nome branch> 
OBS: Passe o nome da branch que foi criada, para então ela mesclar com a default (main)

git pull -> git fetch + git merge
git fetch = baixar conteúdo do repo remoto sem mesclar com o local

Baixar um branch que não existe em seu repo local:
git clone <url>--branch <nome branch> --single-branch

Arquivar alterações:
git stash


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

## Conceitos de Nuvem 
Tipos de serviço de nuvem
IaaS: Infraestrutura como serviço

Eu (cliente) me envolvo mais na configuração, mas tenho mais acesso ao recurso final. Basicamente é você ter um uma estrutura on-premise, porém na nuvem. 
Mais flexível .
Você configura e gerencia o hardware 
MAIOR GESTÃO

PaaS: Plataforma como serviço

Não me preocupo com a máquina onde irá rodar e nem com as configurações da mesma. O foco é na aplicação e suas configurações.
Fornece um ambiente para criação, o teste e a implantação de aplicativos de software, sem focar no gerenciamento da infraestrutura subjacente.
Focado no desenvolvimento de aplicativos
Gerenciamento de plataforma é realizado pelo provedor de nuvem

GESTÃO INTERMEDIÁRIA


SaaS: Software como serviço

É definido pela licença. Cada uma te dá permissão a recursos específicos.
Os usuários se conectam e usam aplicativos com base em nuvem pela internet: 
Ex: Microsoft Teams. Modelo de preço de pagamento conforme o uso. 
MENOR GESTÃO


Modelo de Responsabilidade Compartilhada


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

# Módulo 2 - Benefícios da Nuvem

Alta disponibilidade: recurso disponível sempre que necessário
SLA: Service Level Agreement. (Acordo Nível de Serviço)
Serviços entregáveis da Microsoft
		Caso o serviço fique indisponível, a Microsoft irá recompensar com cŕeditos no Azure, semelhante ao estorno de uma compra que não ocorreu. Tudo isso deve ser visto conforme o que foi firmado em contrato, se exceder o tempo, aí sim ganha o crédito. 
Porcentagem: Tempo definido por contrato em que um serviço pode ficar indisponível. 

Escalabilidade: Você não paga além dos serviços necessários. Nuvem é baseada em consumo.
 Se você precisar aumentar recursos no meio do projeto, pode fazer sem maiores problemas. 
Elasticidade: Escalar e projetar ambiente com base nas requisições. 
	Adicionar VMs ou containers por meio de expansão.
	Se houver queda significativa na demanda, os recursos podem ser reduzidos horizontalmente (automático ou manual).

Confiabilidade: Por ser descentralizado, a nuvem naturalmente da suporte a uma infraestrutura e resiliente. 
 Permite que você tenha recursos em vários lugares do mundo.
Por estar em várias regiões, os recursos não ficarão totalmente indisponíveis, devido a um evento catastrófico por exemplo. 
Previsibilidade: Microsoft Azure Well-Architected Framework. Confiança para que o cliente sinta-se seguro em migrar para a nuvem. 
Segurança: Azure disponibiliza ferramentas, mas a implementação das mesmas NÃO é responsabilidade da Microsoft. 
Atualização de sistemas, patch de correção, ficam a cargo do cliente. 
	Se você deseja atualizações e manutenções automáticas, implantação de software ou plataforma como serviço podem ser uma estratégia melhor. 

Governança: Auditoria. Validar quem tem acesso a o que. Bloquear acesso  quando a origem for de uma região que ninguém deve acessar.
Gerenciabilidade: A nuvem suporta várias maneiras de gerenciar os recursos 

DICA Sobre SLA: Quanto mais “9”, menos tempo o serviço pode ficar indisponível 

Módulo 3z - Componentes de Arquitetura do Azure


Nem todos os recursos estão disponíveis para todas as regiões

GA = General Availability
Abrangência Global

Região é um grupo de Data Center (DC)
3 datacenters por região
https://learn.microsoft.com/pt-br/azure/reliability/cross-region-replication-azure

Não está disponível para qualquer cliente
Serviços Governamentais dos EUA
	Atende às necessidades de segurança e conformidade das agências federais, governos e seus provedores de soluções. 

Não aparece no portal
Instância separada;
Fisicamente isolada das demais implementações que nao sejam do governo os EUA
Acessível somente a pessoal verificado.

Azure China

Microsoft foi a primeira empresa estrangeira a implementar a nuvem na China. 
As instâncias também ficam separadas e a nuvem do Azure é operada pela 21Vianet.
Todos os dados permanecem na China.
Grupos de Recursos são separados conforme sua finalidade.
Uma conta pode ter várias assinaturas, mas uma assinatura está associada apenas a uma conta.

Grupos Gerenciamento: Semelhante a um domínio. Definir padrões para diferentes assinaturas. 

LGPD não permite que o dado saia do Brasil, então o DRS deve ser dentro do Brasil

https://azure.microsoft.com/pt-br/explore/global-infrastructure
https://datacenters.microsoft.com/globe/explore/


Conjunto de dimensionamento:
Conjunto de disponibilidade: 

Domínio de falha: Rack, separar em pelo menos 3
Domínio de atualização: Linha horizontal. Grupo que separa as máquinas, para que possam ser atualizadas, ao passo que ainda ficam outras disponíveis.

Área de Trabalho Virtual do Azure: Computador remote, assim como um RDP (WTS)
Crie um ambiente completo de virtualização da área de trabalho sem precisar executar outros servidores de gateway
ENTRA, console
Experiência desktop Windows na nuvem, Bloqueia cópia de arquivos

Serviço de contêineres do Azure: 
pod de containers
instância: PaaS
Microsserviços

Aplicativos de Contêiner do Azure: balancear a carga e escalar.

AKS: Serviço de orquestração para contêineres com arquiteturas distribuídas e grande volumes de contêineres

AZURE FUNCTION: PaaS 
Código baseado em eventos é executado quando chamado, sem exigir uma infraestrutura de servidor durante períodos inativos
Solicitação Rest

lift-and-shift: levar como está. Migrar máquina sem fazer alterações

Serviços de Aplicativo do Azure: plataforma totalmente gerenciada para criar, implantar e dimensionar aplicativos Web e APIs rapidamente.
Trabalha com> .NET, .NET Core, Node.js, Java, Python ou php.

Oferta Paas com requisitos de nível corporativo de desempenho, segurança e conformidade.

Serviços de rede Azure
Rede Virtual de Azure (VNet) 
Pontos de extremidade públicos, acessíveis de qualquer lugar na internet
Pontos de extremidade privados
default: subredes não se comunicam, para impedir ataques laterais de atingirem outras redes. 
Emparelhamento de rede conecta às redes privadas diretamente. 
Overlap: ips iguais na mesma rede

Gateway VPN

ExpressRoute: Conexão direta via cabo
Região US 2 = mais barata, por enquanto
Scale-set
Duração da consulta: Valor padrão é 10 minutos

Instância Spot: Você paga um valor bem menor pelo recurso, porém, se outra pessoa (conta) quiser usar esse recurso e optar por pagar o valor cheio, seu recurso será derrubado. 
Essa opção é comumente usada para testes e para desenvolvimento, onde esse recurso pode cair sem grandes problemas.

ARMAZENAMENTO 
Contas de Armazenamento (Storage Account)
Deve ter um nome globalmente exclusivo; 3 a 24 caracteres
Fornecer acesso à internet em todo o mundo;
Determinar os serviços de armazenamento e as opções de redundância.
 LRS e GRS

Modelos de dados:
Blob do Azure: Otimizado para quantidades massivas de dados não estruturados como texto ou dados binários. Aceita todo tipo.

Adicionar disco não interrompe a máquina, mas mudar a família sim.
 
Fila do Azure: Armazenamento de mensagens;
Arquivos do Azure: Compartilhamento de arquivos de rede, Protocolo de Mensagens do Servidor ; \\servidor\compartilhamento$
Tabelas do Azure: chave/atributo para armazenamento de dados estruturados não relacionais com design sem esquema.

Migrações para o Azure

Plataforma de migração unificada;
Intervalo de ferramenta integradas e autônomas
Avaliação e migração. (Legado) 

Azure Data Box (Serviço de Migração Física)
80 TB
Mova os bkps de recuperação de desastre 
Dados criptografados e caixa robusta para o trânsito;
Caso de uso: cliente de uma localidade distante do data center. Conectividade limitada. 

AzCopy

CLI
Copiar blobs ou arquivos de ou para sua conta de armazenamento;
Sincronização em uma direção (

Gerenciamento de Armazenamento do Azure
GUI (Semelhante Windows Explorer)
Compatível com Windows, MacOS, Linux
Conexão direta com o computador
Sincronização bidirecional;

Premium: Cobra toda a quantidade de armazenamento, mesmo que não esteja em uso
Compartilhamento de arquivos:
Protocolo: SMB
Porta: 445


## Segurança do Azure
Microsoft Entra ID: Serviço de gerenciamento de identidades e acessos baseado em nuvem do Microsoft Azure.
OpenID, WSFederation

Entra Connect: Intermediário entre AD on-premise e Entra
Logon único (SSO) Single Sign-on
Gerenciamento de aplicativos
Negócios para Negócios (B2B)
Gerenciamento de dispositivos
Business to Customer (B2C)

Se criar usuário no AD, o mesmo é replicado para a nuvem. Mas se criado na nuvem, não é criado no AD.

Benefícios 
Obtenha os benefícios dos serviços de domínio baseados em nuvem sem gerenciar os controladores do domínio;
Execute aplicativos herdados (que não podem utilizar os padrões de autenticação modernos) na nuvem
Sincronizar automaticamente a partir do Entra ID
Autenticação: 
Identifica a pessoa ou serviço buscando acesso a um recurso;
Solicita credenciais de acesso legítimo;
Base para criar princípios de identidade e controle de acesso seguros. 

      Autorização:
Determinar o nível de acesso de uma pessoa ou serviço autenticado;
Define quais dados eles podem acessar e o que podem fazer com eles
Pessoas devem o menor nível de privilégio possível 

Autenticação multifator


Windows Hello: Validação facial 

B2B do Entra External ID


B2C
Compartilho uma pequena parcela dos meus recursos para o usuário usar

Acesso Condicional 
Associação de usuário ou grupo
Local do IP
Dispositivo
Aplicativo
Detecção de risco

Controle de Acesso baseado em função (RBAC)
Gerenciamento de acesso de granularidade fina;
Divida as tarefas dentro da equipe e conceda somente a quantidade de acessos de que os usuários precisam;
Permissionamentos são herdáveis 

Microsoft Defender para Nuvem
Nativo da nuvem. Serviço de monitoramento 
30 dias trial, depois tem cu$to
Fornece recomendações de segurança;
Detectar e bloquear malware;
analisar e identificar ataques potenciais;
Controle de acesso just-in-time para portas

Entra ID
usuário excluído pode ser restaurado até 30 dias 
Roles = Permissão de uma conta em relação a outra
SSPR = Self Service Password Reset
Entra Connect = Sincronizar com AD On-Premise

## Custos

Tipo de recurso
Consumo: 
pay as you go: Pagar conforme o uso;
modelo de reserva: usar o recurso por x tempo (recebe desconto)

Azure Marketplace
Permite que os clientes encontrem aplicativos e serviços de terceiros 
Quando adicionamos um desses recursos e o mesmo dá problema, precisamos acionar o suporte desse fabricante e não a Microsoft
Calculadora de custo total de propriedade (TCO)
Ferramenta para estimar economia de custos ao migrar para o Azure


Gerenciamento de custos do Azure: definir triggers de consumo. Recomendações.


Marcas (Tags)
Ajuda a filtrar os recursos na fatura, para sabermos do que se trata. 
Não são obrigatórios e nem herdáveis.
Metadados aos recursos do Azure;
Taxonomia de maneira lógica.
Par por nome-valor

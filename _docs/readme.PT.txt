      _____  _     _  _____  _______ _     _ _______ _______ _______
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____

                           { ~ ~ ~ PORTUGU�S ~ ~ ~ }
 CONTE�DO
 1. PRE�MBULO
 2A. COMO INSTALAR (PARA WEB SERVIDORES)
 2B. COMO INSTALAR (PARA CLI)
 3A. COMO USAR (PARA WEB SERVIDORES)
 3B. COMO USAR (PARA CLI)
 4A. NAVEGADOR COMANDOS
 4B. CLI (COMANDO LINHA INTERFACE)
 5. ARQUIVOS INCLU�DOS NESTE PACOTE
 6. CONFIGURA��O OP��ES
 7. ASSINATURA FORMATO
 8. CONHECIDOS COMPATIBILIDADE PROBLEMAS

                                     ~ ~ ~


 1. PRE�MBULO

 Obrigado por usando phpMussel, um PHP script projetado para detectar trojans,
 v�rus, malware e outras amea�as dentro dos arquivos enviados para o seu
 sistema onde quer que o script � enganchado, baseado no assinaturas do
 ClamAV e outros.

 PHPMUSSEL COPYRIGHT 2013 e al�m GNU/GPL V.2 atrav�s do Caleb M (Maikuolan).

 Este script � livre software; voc� pode redistribu�-lo e/ou modific�-lo de
 acordo com os termos da GNU General Public License como publicada pela Free
 Software Foundation; tanto a vers�o 2 da Licen�a, ou (em sua op��o) qualquer
 vers�o posterior. Este script � distribu�do na esperan�a que possa ser �til,
 mas SEM QUALQUER GARANTIA; sem mesmo a impl�cita garantia de COMERCIALIZA��O
 ou ADEQUA��O A UM DETERMINADO FIM. Consulte a GNU General Public License para
 obter mais detalhes <http://www.gnu.org/licenses/>
 <http://opensource.org/licenses/>.

 Um especial obrigado para ClamAV por o projeto inspira��o e para as
 assinaturas que este script utiliza, sem que, o script provavelmente n�o
 existiria, ou no melhor, teria ser de muito limitado valor
 <http://www.clamav.net/>.

 Um especial obrigado para Sourceforge por hospedar os projeto arquivos,
 localizado na <http://sourceforge.net/projects/phpmussel/>, para Spambot
 Security por hospedar os phpMussel discuss�o f�runs, localizado na
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, e para
 adicionais recursos de um n�mero de o assinaturas utilizados atrav�s do
 phpMussel: SecuriteInfo.com <http://www.securiteinfo.com/>, PhishTank
 <http://www.phishtank.com/>, NLNetLabs <http://nlnetlabs.nl/> e outros, e
 um especial obrigado a todos aqueles que apoiam o projeto, a qualquer outra
 pessoa que eu possa ter esquecido de mencionar, e para voc�, por usando o
 script.

 Este documento e seu associado pacote pode ser baixado gratuitamente a partir
 do Sourceforge <http://sourceforge.net/projects/phpmussel/>.

                                     ~ ~ ~


 2A. COMO INSTALAR (PARA WEB SERVIDORES)

 Espero para agilizar este processo via fazendo um instalado em algum momento
 no n�o muito distante futuro, mas at� ent�o, siga estas instru��es para
 trabalhar phpMussel na maioria dos sistemas e CMS:

 1) Por o seu lendo isso, eu estou supondo que voc� j� tenha baixado uma c�pia
    arquivada do script, descomprimido seu conte�do e t�-lo sentado em algum
    lugar em sua m�quina local. A partir daqui, voc� vai querer determinar onde
    no seu host ou CMS pretende colocar esses conte�dos. Um diret�rio como
    /public_html/phpmussel/ ou semelhante (por�m, est� n�o importa qual voc�
    escolher, assumindo que � seguro e algo voc� esteja feliz com) vai bastar�.

 2) Abrir "phpmussel.php", procure a linha que come�a com "$vault=", e
    substituir a string entre as seguintes aspas em nessa linha com a
    verdadeira exata localiza��o do "vault" diret�rio de phpMussel. Voc� vai
    ter notado tal diret�rio no arquivo que voc� tenha baixado (a menos que
    voc� sentir-se a re-codifica��o de todo o script, voc� ter� que manter a
    mesma estrutura de arquivos e diret�rios como era no arquivo
    originalmente). Este diret�rio "vault" deve ser um n�vel al�m do diret�rio
    que o arquivo "phpmussel.php" vai existir� em. Salve o arquivo, feche.

 4) (Opcional; Fortemente recomendado para avan�ados usu�rios, mas n�o
    recomendado para iniciantes ou para os inexperientes): Abrir
    "phpmussel.ini" (localizado dentro "vault") - Este arquivo cont�m todas as
    directivas dispon�veis para phpMussel. Acima de cada op��o deve ser um
    breve coment�rio descrevendo o que faz e para que serve. Ajuste essas
    op��es de como voc� v� o ajuste, conforme o que for apropriado para sua
    particular configura��o. Salve o arquivo, feche.

 4) Carregar os conte�dos (phpMussel e seus arquivos) para o diret�rio que voc�
    tinha decidido anteriormente (voc� n�o precisa o readme.XX.txt ou
    change_log.txt arquivos inclu�do, mas principalmente, voc� deve carregar
    tudo).

 5) CMHOD o "vault" diret�rio para "777". O principal diret�rio armazenar o
    conte�do (o que voc� escolheu anteriormente), geralmente, pode ser deixado
    sozinho, mas o CHMOD status deve ser verificado se voc� j� teve problemas
    de permiss�es no passado no seu sistema (por padr�o, deve ser algo como
    "755").

 6) Seguida, voc� vai precisar "enganchar" phpMussel ao seu sistema ou CMS.
    Existem v�rias diferentes maneiras em que voc� pode "enganchar" scripts
    como phpMussel ao seu sistema ou CMS, mas o mais f�cil � simplesmente
    incluir o script no in�cio de um n�cleo arquivo de seu sistema ou CMS (uma
    que vai geralmente sempre ser carregado quando algu�m acessa qualquer
    p�gina atrav�s de seu site) utilizando um require ou include comando.
    Normalmente, isso vai ser algo armazenado em um diret�rio como "/includes",
    "/assets" ou "/functions", e muitas vezes, ser nomeado algo como
    "init.php", "common_functions.php", "functions.php" ou semelhante. Voc�
    precisar� determinar qual arquivo isso � para a sua situa��o. Para fazer
    isso, insira a seguinte linha de c�digo para o in�cio desse n�cleo arquivo,
    substituindo a string contida dentro das aspas com o exato endere�o do
    "phpmussel.php" arquivo (endere�o local, n�o o endere�o HTTP; ser�
    semelhante ao vault endere�o mencionado anteriormente).

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Salve o arquivo, fechar, recarregar-lo.

 7) Neste ponto, voc� est� feito! Por�m, voc� provavelmente deve test�-lo para
    garantir que ele est� funcionando corretamente. Para testar as arquivo
    carregamento prote��o, tentar carregar dos testes arquivos inclu�dos no
    pacote em "_testfiles" para seu site atrav�s de seus habitual navegador
    carregamentos m�todos. Se tudo estiver funcionando, a mensagem deve
    aparecer a partir phpMussel confirmando que o carregamento foi bloqueado
    com sucesso. Se nada aparecer, algo est� n�o funcionando corretamente. Se
    voc� estiver usando quaisquer avan�ados recursos ou se voc� estiver usando
    outros tipos de an�lisar poss�vel com a ferramenta, Eu sugiro tentar isso
    com aqueles para certificar que ele funciona como esperado, tamb�m.

                                     ~ ~ ~


 2B. COMO INSTALAR (PARA CLI)

 Espero para agilizar este processo via fazendo um instalado em algum momento
 no n�o muito distante futuro, mas at� ent�o, siga estas instru��es para obter
 phpMussel pronto para trabalhar com CLI (estar ciente, neste momento, CLI
 apoio s� se aplica a sistemas baseados no Windows; Linux e outros sistemas
 ser� em breve para uma posterior vers�o do phpMussel):

 1) Por o seu lendo isso, eu estou supondo que voc� j� tenha baixado uma c�pia
    arquivada do script, descomprimido seu conte�do e t�-lo sentado em algum
    lugar em sua m�quina local. Quando voc� tiver determinado que voc� est�
    feliz com o localiza��o escolhido para phpMussel, continuar.

 2) phpMussel requer php para ser instalado na host m�quina a fim de executar.
    Se voc� n�o ainda tno PHP instalado em sua m�quina, por favor instalar o
    PHP em sua m�quina, seguindo as instru��es fornecidas pelo php instalador.

 2) Abrir "phpmussel.php", procure a linha que come�a com "$vault=", e
    substituir a string entre as seguintes aspas em nessa linha com a
    verdadeira exata localiza��o do "vault" diret�rio de phpMussel. Voc� vai
    ter notado tal diret�rio no arquivo que voc� tenha baixado (a menos que
    voc� sentir-se a re-codifica��o de todo o script, voc� ter� que manter a
    mesma estrutura de arquivos e diret�rios como era no arquivo
    originalmente). Este diret�rio "vault" deve ser um n�vel al�m do diret�rio
    que o arquivo "phpmussel.php" vai existir� em. Salve o arquivo, feche.

 4) (Opcional; Fortemente recomendado para avan�ados usu�rios, mas n�o
    recomendado para iniciantes ou para os inexperientes): Abrir
    "phpmussel.ini" (localizado dentro "vault") - Este arquivo cont�m todas as
    directivas dispon�veis para phpMussel. Acima de cada op��o deve ser um
    breve coment�rio descrevendo o que faz e para que serve. Ajuste essas
    op��es de como voc� v� o ajuste, conforme o que for apropriado para sua
    particular configura��o. Salve o arquivo, feche.

 5) (Opcional) Voc� pode fazer usando phpMussel no modo CLI mais f�cil para si
    mesmo atrav�s da cria��o de um batch arquivo para carregar automaticamente
    php e phpMussel. Para fazer isso, abra um editor de simples texto como
    Notepad ou Notepad++, digite o completo caminho para o "php.exe" arquivo no
    php instala��o diret�rio, seguido por um espa�o, seguido pelo completo
    caminho para o "phpmussel.php" arquivo no diret�rio da sua phpMussel
    instala��o, salvar o arquivo com a extens�o ".bat" Em algum lugar que voc�
    vai encontr�-lo facilmente, e clique duas vezes nesse arquivo para executar
    phpMussel no futuro.

 6) Neste ponto, voc� est� feito! Por�m, voc� provavelmente deve test�-lo para
    garantir que ele est� funcionando corretamente. Para testar phpMussel,
    executar phpMussel e tente an�lizar o diret�rio "_testfiles" fornecida com
    o pacote.

                                     ~ ~ ~


 3A. COMO USAR (PARA WEB SERVIDORES)

 phpMussel � um script destinado a funcionar de adequadamente, sem
 complica��es, com um m�nimo n�vel de requisitos por voc�: Ap�s ter sido
 instalado, basicamente, ele simplesmente deve funcionar.

 An�lise dos arquivos carregamentos � automatizado e ativado por padr�o, por
 isso nada � exigido por voc� por essa particular fun��o.

 Por�m, voc� tamb�m � capaz de instruir phpMussel para analisar arquivos ou
 diret�rios que voc� especificar implicitamente. Para fazer isso, em primeiro
 lugar, voc� vai precisar para assegurar que apropriada configura��o � definida
 no phpmussel.ini arquivo (cleanup deve ser desativado), e quando feito, em um
 php arquivo que est� enganchado ao phpMussel, usar a seguinte fun��o no seu
 c�digo:

 phpMussel($what_to_scan,$output_type,$output_flatness);

 Onde:
 - $what_to_scan � uma string ou um array, apontando para um alvo arquivo, um
   alvo diret�rio ou um array de alvo arquivos e/ou alvo diret�rios.
 - $output_type � um integer, indicando o formato no qual os resultados da
   an�lise s�o regresso se. Um valor de 0 instrui a fun��o para retornar
   resultados como um integer (um resultado retornado de -2 indica que corrupto
   dados foi detectado durante a an�lise, e portanto, a an�lise n�o foi
   conclu�da, -1 indica que extens�es ou complementos necess�rios pelo php para
   executar a an�lise estavam faltando, e portanto, a an�lise n�o foi
   conclu�da, 0 indica que o alvo de an�lise n�o existe, e portanto, havia nada
   para analisar, 1 indica que o alvo foi analisado e n�o problemas foram
   detectados, e 2 indica que o alvo foi analisado e problemas foram
   detectados). Um valor de 1 instrui a fun��o para retornar resultados como
   humano leg�vel texto. Um valor de 2 instrui a fun��o para retornar
   resultados como humano leg�vel texto e para exportar os resultados para um
   global vari�vel. Esta vari�vel � opcional, padronizando a 0.
 - $output_flatness � um integer, indicando se a permitir que os resultados
   sejam retornados como uma array ou n�o. Normalmente, se o alvo de an�lise
   continha v�rios itens (tal como se um diret�rio ou array) os resultados
   ser�o retornados em uma array (padr�o valor de 0). Um valor de 1 instrui a
   fun��o a implodir qualquer array antes de entrada, resultando em uma
   achatada string contendo os resultados a serem retornados. Esta vari�vel �
   opcional, padronizando a 0.

 Exemplos:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Retorna algo tal como esta (como uma string):
    Wed, 16 Sep 2013 02:49:46 +0000 Come�ado.
    > Verifica��o '/user_name/public_html/my_file.html':
    -> N�o problemas encontrados.
    Wed, 16 Sep 2013 02:49:47 +0000 Terminado.

 Por completos detalhes sobre que tipo de assinaturas phpMussel usa durante a
 an�lise e como ele usa essas assinaturas, consulte a Assinatura Formato se��o
 deste arquivo README.

 Se voc� encontrar quaisquer falsos positivos, se voc� encontrar algo novo que
 voc� acha deve ser bloqueado, ou para qualquer outra coisa com rela��o a
 assinatura, entre em contato comigo sobre isso para que eu possa fazer as
 mudan�as necess�rias, que, se voc� n�o entrar em contato comigo, eu posso n�o
 ser necessariamente conscientes de.

 Para desativar as assinaturas que est�o inclu�dos com phpMussel (tal como se
 voc� est� experimentando falsos positivos espec�fico para seus fins que n�o
 deve normalmente ser removidos da agilize), consulte as notas sobre
 Greylisting dentro do Navegador Comandos se��o deste README arquivo.

 Al�m da padr�o arquivo carregamento an�lise e a opcional an�lise de outros
 arquivos e/ou diret�rios especificado atrav�s da fun��o acima, inclu�do no
 phpMussel � uma fun��o destinada � an�lise do corpo das e-mail mensagens. Esta
 fun��o funciona da mesma forma para a phpMussel() fun��o, mas se concentra
 exclusivamente em fazer a compara��o com as assinaturas de ClamAV baseiam
 e-mail. Eu tenho amarrei essas assinaturas para a padr�o phpMussel() fun��o,
 porque � muito pouco prov�vel que voc� jamais encontrar o corpo de uma
 recebidos e-mail mensagem na necessidade de an�lise dentro um arquivo
 carregamento direcionado para uma p�gina onde phpMussel � enganchada, e assim,
 para amarrar essas assinaturas para a phpMussel() fun��o seria redundante.
 Mas, o que disse, tendo uma separada fun��o para comparar contra essas
 assinaturas poderia revelar-se extremamente �til para alguns, especialmente
 para aqueles cuja CMS ou webfront sistema est� de alguma modo enganchado em
 seu e-mail sistema e para aqueles de quem analisar seus e-mails atrav�s de um
 php script de que eles poderiam engancho para phpMussel. Configura��o para
 esta fun��o, como todos os outros, � controlado atrav�s do phpmussel.ini
 arquivo. Para utilizar esta fun��o (voc� vai precisar para fazer a sua
 pr�pria implementa��o) em um php arquivo que est� enganchado ao phpMussel,
 usar a seguinte fun��o no seu c�digo:

 phpMussel_mail($body);

 Onde $body � o corpo da email mensagem que voc� deseja analisar (Al�m, voc�
 pode tentar analisar novos f�rum posts, mensagens do seu on-line contato form
 ou similar). Se algum erro ocorrer impedindo a fun��o de completar a sua
 an�lise, um valor de -1 ser� retornado. Se a fun��o faz completa a sua an�lise
 e detecta nada, um valor de 0 ser� retornado (ou seja, limpo). Se, contudo, a
 fun��o faz detectar algo, uma string ser� retornado contendo uma mensagem
 declarando o que foi detectado.

 Al�m do acima, se voc� olhar para o c�digo-fonte, voc� pode notar a fun��o
 phpMusselD() e phpMusselR(). Estas fun��es s�o sub-fun��es de phpMussel(), e
 n�o deve ser chamado diretamente fora dessa pai fun��o (n�o por causa de
 adversos efeitos.. Mais-lo, simplesmente porque ele tinha nenhuma utilidade, e
 provavelmente n�o ir� realmente funcionar corretamente qualquer maneira).

 Existem muitos outros controlos e fun��es dispon�veis dentro phpMussel para
 seu uso, tamb�m. Para qualquer esses controlos e fun��es que, at� o final
 desta se��o do README, ainda n�o foram documentados, por favor, continue a
 leitura e consulte o Navegador Comandos se��o deste README arquivo.

                                     ~ ~ ~


 3B. COMO USAR (PARA CLI)

 Por favor, consulte ao "COMO INSTALAR (PARA CLI)" se��o deste README arquivo.

 Esteja ciente de que, embora futuras vers�es do phpMussel deve apoiar outros
 sistemas, at this time, phpMussel CLI modo suporte s� � otimizado para uso em
 sistemas baseados no Windows (voc� pode, � claro, experiment�-lo em outros
 sistemas, mas eu n�o posso garantir que vai funcionar como pretendido).

 Tamb�m estar ciente de que phpMussel n�o � o funcional equivalente de um
 completa antiv�rus su�te, e contr�rio de convencionais antiv�rus su�tes, n�o
 monitora ativa mem�ria ou detectar v�rus proativamente! Ele s� ir� detectar
 v�rus contidos por esses espec�ficos arquivos que voc� explicitamente diga a
 ele analisar.

                                     ~ ~ ~


 4A. NAVEGADOR COMANDOS

 Quando phpMussel � instalado e funcionando corretamente no seu sistema, se
 voc� tem configur� as vari�veis script_password e logs_password no seu
 configura��o arquivo, voc� ser� capaz de executar um limitado n�mero de
 administrativas fun��es e entrada um algum n�mero de comandos para phpMussel
 atrav�s de seu navegador. A raz�o pela qual essas senhas precisam ser
 definidas a fim de permitir que esses controles do navegador � tanto para
 garantir adequada seguran�a, adequada prote��o desses navegador controles e
 para garantir que existe uma maneira por desses navegador controles para ser
 totalmente desativado se eles n�o s�o desejadas por voc� e/ou outros
 webmestres/administradores usando phpMussel. Portanto, em outras palavras,
 para ativar esses controles, definir uma senha, e para desativar esses
 controles, definir nenhum senha. Alternativamente, se voc� optar por ativar
 esses controles ent�o optar por desativar esses controles em um posterior
 data, existe um comando para fazer isto (tal pode ser �til se voc� executar
 algumas a��es que voc� sente poderia comprometer as senhas delegados e precisa
 para desativar rapidamente esses controles sem modificar o configura��o
 arquivo).

 Algumas raz�es pelas quais voc� -deve- ativar esses controles:
 - Fornece uma maneira para greylist assinaturas em casos como quando voc�
   descobre uma assinatura que est� produzindo um falso-positivo durante o
   carregar de arquivos para o seu sistema e voc� n�o tem tempo para
   manualmente editar e recarregar o greylist arquivo.
 - Fornece uma maneira por voc� para permitir algu�m diferente de si mesmo para
   controlar a sua c�pia do phpMussel sem a impl�cita necessidade a dar o
   acesso ao FTP.
 - Fornece uma maneira de fornecer controlado acesso aos seus log arquivos.
 - Fornece um f�cil maneira para atualizar phpMussel quando atualiza��es s�o
   dispon�veis.
 - Fornece uma maneira por voc� para monitorar phpMussel quando FTP acesso ou
   outras convencionais vias de acesso para monitoramento phpMussel n�o est�o
   dispon�veis.

 Algumas raz�es pelas quais voc� -n�o- deve ativar esses controles:
 - Fornece um vetor por potenciais atacantes e indesej�veis para determinar se
   ou n�o voc� est� usando phpMussel (embora, este poderia ser tanto uma raz�o
   por e uma raz�o contra, dependendo em perspectiva) por cegamente envio de
   comandos para os servidores como meio para sondar. Por um lado, isso pode
   desencorajar os atacantes de testando seu sistema, se eles descobrem que
   voc� est� usando phpMussel, assumindo que eles est�o sondando por raz�es que
   o sua m�todo de ataque � desprovido de efeito como resultado do seu uso de
   phpMussel. Mas, por outro lado, se algum imprevisto e presentemente
   desconhecidos vulnerabilidade dentro phpMussel ou um futuro vers�o dos
   mesmos trata de luz, e se ele poderia fornecer um vetor de ataque, um
   positivo resultado de tal sondando poderia incentivar os atacantes de
   testando seu sistema.
 - Se suas senhas delegados foram comprometidos, se n�o alterado, pode fornecer
   uma maneira para um atacante para ignorar o que quer assinaturas podem ser
   de outra forma normalmente preven��o sucesso de seus ataques, ou at� mesmo
   potencialmente desativar phpMussel completamente, proporcionando uma forma
   de tornar a efic�cia da phpMussel discut�vel.

 De qualquer maneira, independentemente do que voc� escolher, a escolha final �
 sua. Por padr�o, esses controles ser�o desativados, mas ter um pensar sobre
 isso, e se voc� decidir que voc� quer eles, Nesta se��o explica tanto como
 habilit�-los e como us�-los.

 A lista de dispon�veis browser comandos:

 scan_log
   Senha necess�ria: logs_password
   Outros requisitos: scan_log deve ser definido.
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?logspword=[logs_password]&phpmussel=scan_log
   ~
   Que faz: Imprime o conte�do de seu scan_log arquivo para a tela.
   ~
 scan_kills
   Senha necess�ria: logs_password
   Outros requisitos: scan_kills deve ser definido.
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?logspword=[logs_password]&phpmussel=scan_kills
   ~
   Que faz: Imprime o conte�do de seu scan_kills arquivo para a tela.
   ~
 controls_lockout
   Senha necess�ria: logs_password OU script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo 1: ?logspword=[logs_password]&phpmussel=controls_lockout
   Exemplo 2: ?pword=[script_password]&phpmussel=controls_lockout
   ~
   Que faz: Desativa todos os navegador controles. Isso deve ser usado se voc�
            suspeitar que qualquer das senhas foram comprometidas (isso pode
            acontecer se voc� estiver usando esses controles a atrav�s de um
            computador que n�o � seguro ou n�o � confi�vel). controls_lockout
            funciona atrav�s de criando um arquivo, controls.lck, no seu vault,
            de que phpMussel ir� olhar por antes de executar qualquer comando
            de qualquer variedade. Quando isso acontece, para reativar os
            controlos, voc� precisar� manualmente deletar o controls.lck
            arquivo atrav�s de FTP ou semelhante. Pode ser chamado usando
            qualquer senha.
   ~
 disable
   Senha necess�ria: script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?pword=[script_password]&phpmussel=disable
   ~
   Que faz: Desativar phpMussel. Isso deve ser usado se voc� estiver executando
            quaisquer atualiza��es ou altera��es no seu sistema ou se est�
            instalando qualquer novo software ou m�dulos para seu sistema que
            fazer ou potencialmente poderiam desencadear falsos positivos. Isso
            tamb�m deve ser usado se voc� est� tendo problemas com phpMussel
            mas n�o deseja remov�-lo do sistema. Quando isso acontece, para
            reativar phpMussel, uso "enable".
   ~
 enable
   Senha necess�ria: script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?pword=[script_password]&phpmussel=enable
   ~
   Que faz: Ativar phpMussel. Este deve ser usado se voc� j� desativado
            phpMussel usando "disable" e desejar para reativ�-la.
   ~
 update
   Senha necess�ria: script_password
   Outros requisitos: update.dat and update.inc must exist.
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: forcedupdate
   Exemplo: ?pword=[script_password]&phpmussel=update&musselvar=forcedupdate
   ~
   Que faz: Verifica se h� atualiza��es para ambos phpMussel e suas
            assinaturas. Se as atualiza��o verifica��es suceder e atualiza��es
            s�o encontrados, tentar� baixar e instalar essas atualiza��es. Se
            atualiza��es s�o verificados muito rapidamente, atualiza��o
            verifica��o ir� abortar. Se atualiza��o verifica��o falha,
            atualiza��o ir� abortar. Se opcional par�metro "forcedupdate" �
            fornecido, hora da �ltima atualiza��o ser� ignorada, e assim,
            atualizar verifica��o ser� continuar� mesmo que est� sendo
            verificado "muito rapidamente", mas ainda vai abortar se a
            atualiza��o verifica��o falha. Os resultados de o inteiro processo
            s�o impressos na tela. Eu recomendo incluindo opcional par�metro
            "forcedupdate" se voc� est� manualmente acionando esse controle,
            mas por favor, n�o uso "forcedupdate" se voc� estiver automatizando
            o processo, tal como atrav�s de cron ou semelhante. Eu recomendo
            verificando pelo menos uma vez por m�s para garantir que seus
            assinaturas e sua c�pia do phpMussel s�o mantidos atualizados
            (A menos, claro, voc� est� verificando se h� atualiza��es e
            instal�-los manualmente, que, eu ainda recomendo fazer pelo menos
            um por m�s). Verificando mais de que duas vezes por m�s �
            provavelmente in�til, considerando que eu (no momento de escrever
            este) estou trabalhando neste projeto sozinho e eu estou muito
            improv�vel que seja capaz de produzir atualiza��es de qualquer
            variedade com mais freq��ncia do que (nem eu particularmente quero
            para a maior parte).
   ~
 greylist
   Senha necess�ria: script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: [Nome de assinatura a ser greylisted]
   Par�metros opcionais: (nenhum)
   Exemplo: ?pword=[script_password]&phpmussel=greylist&musselvar=[Signature]
   ~
   Que faz: Adicionar uma assinatura para o greylist.
   ~
 greylist_clear
   Senha necess�ria: script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?pword=[script_password]&phpmussel=greylist_clear
   ~
   Que faz: Limpo inteiro greylist.
   ~
 greylist_show
   Senha necess�ria: script_password
   Outros requisitos: (nenhum)
   Par�metros necess�rios: (nenhum)
   Par�metros opcionais: (nenhum)
   Exemplo: ?pword=[script_password]&phpmussel=greylist_show
   ~
   Que faz: Imprime o conte�do da greylist para a tela.
   ~

                                     ~ ~ ~


 4B. CLI (COMANDO LINHA INTERFACE)

 phpMussel pode ser executado como um interativo arquivo analisador no CLI modo
 em sistemas baseados em Windows. Por favor, consulte ao
 "COMO INSTALAR (PARA CLI)" se��o deste README arquivo por mais detalhes.

 Por uma lista de comandos dispon�veis Em CLI, no CLI prompt, digite 'c', e
 pressione Enter.

                                     ~ ~ ~


 5. ARQUIVOS INCLU�DOS NESTE PACOTE

 O seguinte est� uma lista de todos os arquivos que deveria sido inclu�dos na
 arquivada c�pia desse script quando voc� baixado-lo, todos os arquivos que
 podem ser potencialmente criados como resultado de seu uso deste script,
 juntamente com uma breve descri��o do que todos esses arquivos s�o por.

 /phpmussel.php (Script, Inclu�do)
    phpMussel carregador arquivo. Carrega o principal script, atualizador, etc.
    Isto � o que voc� deveria ser enganchando em (essencial)!
    ~
 /web.config (Outro, Inclu�do)
    Um ASP.NET configura��o arquivo (neste caso, para proteger o "vault"
    diret�rio contra serem acessado por fontes n�o autorizadas em caso que o
    script est� instalado em um servidor baseado em ASP.NET tecnologias).
    ~
 /_docs/ (Diret�rio)
    Documenta��o diret�rio (cont�m v�rios arquivos).
    ~
 /_docs/change_log.txt (Documenta��o, Inclu�do)
    Um registro das mudan�as feitas para o script entre o diferentes vers�es
    (n�o � necess�rio para o correto funcionamento do script).
    ~
 /_docs/readme.DE.txt (Documenta��o, Inclu�do); DEUTSCH
 /_docs/readme.EN.txt (Documenta��o, Inclu�do); ENGLISH
 /_docs/readme.ES.txt (Documenta��o, Inclu�do); ESPA�OL
 /_docs/readme.FR.txt (Documenta��o, Inclu�do); FRAN�AIS
 /_docs/readme.ID.txt (Documenta��o, Inclu�do); BAHASA INDONESIA
 /_docs/readme.IT.txt (Documenta��o, Inclu�do); ITALIANO
 /_docs/readme.NL.txt (Documenta��o, Inclu�do); NEDERLANDSE
 /_docs/readme.PT.txt (Documenta��o, Inclu�do); PORTUGU�S
    O README arquivos (por exemplo; o arquivo que voc� est� lendo atualmente).
    ~
 /_docs/signatures_tally.txt (Documenta��o, Inclu�do)
    Contagem registro dos assinaturas inclu�dos (n�o � necess�rio para o
    correto funcionamento do script).
    ~
 /_testfiles/ (Diret�rio)
    Teste arquivo diret�rio (cont�m v�rios arquivos).
    Todos os arquivos contidos s�o teste arquivos para testar se phpMussel foi
    instalado corretamente no seu sistema, e voc� n�o precisa carregar desse
    diret�rio ou qualquer de seus arquivos, exceto ao fazer tais testando.
    ~
 /_testfiles/ascii_standard_testfile.txt (Test file, Inclu�do)
    Teste arquivo para testar phpMussel normalizada ASCII assinaturas.
    ~
 /_testfiles/coex_testfile.rtf (Test file, Inclu�do)
    Teste arquivo para testar phpMussel complexos estendidas assinaturas.
    ~
 /_testfiles/exe_standard_testfile.exe (Test file, Inclu�do)
    Teste arquivo para testar phpMussel PE assinaturas.
    ~
 /_testfiles/general_standard_testfile.txt (Test file, Inclu�do)
    Teste arquivo para testar phpMussel gerais assinaturas.
    ~
 /_testfiles/graphics_standard_testfile.gif (Test file, Inclu�do)
    Teste arquivo para testar phpMussel gr�ficas assinaturas.
    ~
 /_testfiles/html_standard_testfile.txt (Test file, Inclu�do)
    Teste arquivo para testar phpMussel normalizada HTML assinaturas.
    ~
 /_testfiles/md5_testfile.txt (Test file, Inclu�do)
    Teste arquivo para testar phpMussel MD5 assinaturas.
    ~
 /_testfiles/metadata_testfile.txt.gz (Test file, Inclu�do)
    Teste arquivo por testando phpMussel metadados assinaturas e por testando
    GZ arquivo suport no seu sistema.
    ~
 /_testfiles/metadata_testfile.zip (Test file, Inclu�do)
    Teste arquivo por testando phpMussel metadados assinaturas e por testando
    ZIP arquivo suport no seu sistema.
    ~
 /_testfiles/ole_testfile.ole (Test file, Inclu�do)
    Teste arquivo para testar phpMussel OLE assinaturas.
    ~
 /_testfiles/pdf_standard_testfile.pdf (Test file, Inclu�do)
    Teste arquivo para testar phpMussel PDF assinaturas.
    ~
 /_testfiles/pe_sectional_testfile.exe (Test file, Inclu�do)
    Teste arquivo para testar phpMussel PE Seccional assinaturas.
    ~
 /_testfiles/xdp_standard_testfile.xdp (Test file, Inclu�do)
    Teste arquivo para testar phpMussel XML/XDP-Peda�o assinaturas.
    ~
 /vault/ (Diret�rio)
    Vault diret�rio (cont�m v�rios arquivos).
    ~
 /vault/quarantine/ (Diret�rio)
    Quarentena diret�rio (cont�m os arquivos em quarentena).
    ~
 /vault/quarantine/.htaccess (Outro, Inclu�do)
    Um hipertexto acesso arquivo (neste caso, para proteger confidenciais
    arquivos pertencentes ao script contra serem acessados por fontes n�o
    autorizadas).
    ~
 /vault/.htaccess (Outro, Inclu�do)
    Um hipertexto acesso arquivo (neste caso, para proteger confidenciais
    arquivos pertencentes ao script contra serem acessados por fontes n�o
    autorizadas).
    ~
 /vault/ascii_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ascii_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/ascii_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/ascii_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/ascii_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ascii_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/ascii_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ascii_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por normalizada ASCII assinaturas.
    Necess�rio se o normalizada ASCII assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/coex_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/coex_custom.cvd (Assinaturas, Inclu�dos)
 /vault/coex_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivos por o complexos estendidas assinaturas.
    Necess�rio se o complexos estendidas assinaturas op��o em phpmussel.ini
    est� ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/elf_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/elf_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/elf_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/elf_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/elf_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/elf_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/elf_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/elf_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por ELF assinaturas.
    Necess�rio se o ELF assinaturas op��o em phpmussel.ini est� ativado. Pode
    remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/exe_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/exe_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/exe_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/exe_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/exe_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/exe_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/exe_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/exe_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por Port�til Execut�vel arquivo (EXE) assinaturas.
    Necess�rio se o EXE assinaturas op��o em phpmussel.ini est� ativado. Pode
    remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/filenames_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/filenames_custom.cvd (Assinaturas, Inclu�dos)
 /vault/filenames_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivos por arquivo nome assinaturas.
    Necess�rio se o arquivo nome assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/general_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/general_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/general_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/general_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/general_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/general_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/general_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/general_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por gerais assinaturas.
    Necess�rio se o gerais assinaturas op��o em phpmussel.ini est� ativado.
    Pode remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/graphics_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/graphics_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/graphics_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/graphics_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/graphics_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/graphics_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/graphics_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/graphics_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por gr�ficas assinaturas.
    Necess�rio se o gr�ficas assinaturas op��o em phpmussel.ini est� ativado.
    Pode remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/greylist.csv (Assinaturas, Inclu�dos/Criados)
    CSV de greylisted assinaturas indicando a phpMussel quais assinaturas deve
    ser ignorado (arquivo automaticamente recriado se deletado).
    ~
 /vault/hex_general_commands.csv (Assinaturas, Inclu�dos)
    Hex-codificado CSV de geral comando detec��es opcionalmente usado por
    phpMussel. Necess�rio se o geral comando detec��es op��o em phpmussel.ini
    est� ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/html_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/html_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/html_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/html_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/html_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/html_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/html_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/html_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por normalizada HTML assinaturas.
    Necess�rio se o normalizada HTML assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/lang.inc (Script, Inclu�do)
    phpMussel Linguagem Dados; Necess�rio por multilingues capacidades.
    ~
 /vault/macho_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/macho_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/macho_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/macho_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/macho_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/macho_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/macho_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/macho_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por Mach-O assinaturas.
    Necess�rio se o Mach-O assinaturas op��o em phpmussel.ini est� ativado.
    Pode remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/mail_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/mail_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/mail_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/mail_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/mail_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/mail_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/mail_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/mail_mussel_standard.cvd (Assinaturas, Inclu�dos)
 /vault/mail_mussel_standard.map (Assinaturas, Inclu�dos)
    Arquivos por assinaturas usado por a phpMussel_mail() fun��o.
    Necess�rio se o phpMussel_mail() fun��o � utilizado em qualquer forma.
    Pode remover se n�o usado (mas os arquivos ser�o recriados na atualiza��o).
    ~
 /vault/md5_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/md5_custom.cvd (Assinaturas, Inclu�dos)
 /vault/md5_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivos por MD5 baseadas assinaturas.
    Necess�rio se o MD5 baseadas assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/metadata_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/metadata_custom.cvd (Assinaturas, Inclu�dos)
 /vault/metadata_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivos por metadados assinaturas.
    Necess�rio se o metadados assinaturas op��o em phpmussel.ini est� ativado.
    Pode remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/ole_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ole_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/ole_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/ole_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/ole_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ole_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/ole_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/ole_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por OLE assinaturas.
    Necess�rio se OLE assinaturas op��o em phpmussel.ini est� ativado. Pode
    remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/pdf_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/pdf_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/pdf_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/pdf_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/pdf_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/pdf_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/pdf_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/pdf_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por PDF assinaturas.
    Necess�rio se PDF assinaturas op��o em phpmussel.ini est� ativado. Pode
    remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/pe_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/pe_custom.cvd (Assinaturas, Inclu�dos)
 /vault/pe_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivos por PE Seccional assinaturas.
    Necess�rio se o PE Seccional assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/phpmussel.inc (Script, Inclu�do)
    phpMussel N�cleo Script; O principal corpo de phpMussel (essencial)!
    ~
 /vault/phpmussel.ini (Outro, Inclu�do)
    phpMussel configura��o arquivo; Cont�m todas ao configura��o op��es de
    phpMussel, dizendo-lhe o que fazer e como operar corretamente (essencial)!
    ~
 /vault/scan_log.txt *(Logfile, Criado)
    Um registro de tudo analisado por phpMussel.
    ~
 /vault/scan_kills.txt *(Logfile, Criado)
    Um registro de tudos os arquivos carregamentos bloqueado ou matado por
    phpMussel.
    ~
 /vault/swf_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/swf_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/swf_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/swf_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/swf_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/swf_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/swf_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/swf_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por o Shockwave assinaturas.
    Necess�rio se o Shockwave assinaturas op��o em phpmussel.ini est� ativado.
    Pode remover se a op��o � desativado (mas os arquivos ser�o recriados na
    atualiza��o).
    ~
 /vault/template.html (Outro, Inclu�do)
    phpMussel template arquivo; Template por HTML produzido atrav�s do
    phpMussel por o bloqueado arquivo carregamento mensagem (a mensagem visto
    por o carregador).
    ~
 /vault/update.dat (Outro, Inclu�do)
    Arquivo contendo informa��es sobre a vers�o por tanto script e assinaturas
    de phpMussel. Se voc� est� tencionando automaticamente atualizar phpMussel
    ou deseja atualizar phpMusel atrav�s de seu navegador, este arquivo �
    essencial.
    ~
 /vault/update.inc (Script, Inclu�do)
    phpMussel Atualiza��o Script; Necess�rio por autom�ticas atualiza��es e
    para atualizar phpMussel atrav�s de seu navegador, mas n�o � necess�rio
    contr�rio.
    ~
 /vault/whitelist_clamav.cvd (Assinaturas, Inclu�dos)
 /vault/whitelist_custom.cvd (Assinaturas, Inclu�dos)
 /vault/whitelist_mussel.cvd (Assinaturas, Inclu�dos)
    Arquivo espec�fico whitelist.
    Necess�rio se o whitelist op��o em phpmussel.ini est� ativado e se voc�
    deseja ter espec�ficos arquivos whitelisted. Pode remover se a op��o �
    desativado ou se voc� n�o precisa whitelisting (mas os arquivos ser�o
    recriados na atualiza��o).
    ~
 /vault/xmlxdp_clamav_regex.cvd (Assinaturas, Inclu�dos)
 /vault/xmlxdp_clamav_regex.map (Assinaturas, Inclu�dos)
 /vault/xmlxdp_clamav_standard.cvd (Assinaturas, Inclu�dos)
 /vault/xmlxdp_clamav_standard.map (Assinaturas, Inclu�dos)
 /vault/xmlxdp_custom_regex.cvd (Assinaturas, Inclu�dos)
 /vault/xmlxdp_custom_standard.cvd (Assinaturas, Inclu�dos)
 /vault/xmlxdp_mussel_regex.cvd (Assinaturas, Inclu�dos)
 /vault/xmlxdp_mussel_standard.cvd (Assinaturas, Inclu�dos)
    Arquivos por XML/XDP-Peda�o assinaturas.
    Necess�rio se XML/XDP-Peda�o assinaturas op��o em phpmussel.ini est�
    ativado. Pode remover se a op��o � desativado (mas os arquivos ser�o
    recriados na atualiza��o).
    ~

 * Arquivo nome podem variar baseado em configura��o estipula��o
   (referem-se a phpmussel.ini).

 = EM RELA��O AOS ASSINATURAS ARQUIVOS =
    CVD � um acr�nimo por "ClamAV Virus Definitions", em refer�ncia tanto �
    forma como ClamAV refere-se �s suas pr�prias assinaturas e para o uso
    dessas assinaturas por phpMussel; Arquivos que terminam com "CVD" cont�m
    assinaturas.
    ~
    Arquivos que terminam com "MAP", literalmente, mapa quais assinaturas
    phpMussel deve e n�o deve ser usado para an�lisar arquivos; Nem todas as
    assinaturas s�o necessariamente necess�rio por cada individual an�lise, e
    assim, phpMussel usa mapas dos assinatura arquivos para acelerar o processo
    de an�lise (um processo que de outro modo seria extremamente lento e
    tedioso).
    ~
    Assinatura arquivos marcados com "_regex" cont�m assinaturas que utilizam
    regulares express�es (regex).
    ~
    Assinatura arquivos marcados com "_standard" cont�m assinaturas que
    especificamente n�o utilizam qualquer forma de regulares express�es.
    ~
    Assinatura arquivos marcados com nenhum "_regex" nem "_standard" ser� como
    um ou outro, mas n�o tanto (consulte Assinatura Formato se��o deste README
    arquivo por documenta��o e espec�ficos detalhes).
    ~
    Assinatura arquivos marcados com "_clamav" cont�m assinaturas, provenientes
    exclusivamente do ClamAV database (GNU/GPL).
    ~
    Assinatura arquivos marcados com "_custom", por padr�o, n�o cont�m qualquer
    assinatura; Esses arquivos existem para dar-lhe um lugar para colocar suas
    pr�prias personalizadas assinaturas, se voc� criar algum do seu pr�prio.
    ~
    Assinatura arquivos marcados com "_mussel" cont�m assinaturas que s�o
    especificamente n�o provenientes de ClamAV, assinaturas que, em geral, eu
    criei pessoalmente ou baseado em informa��es obtidas atrav�s de v�rias
    fontes.
    ~

                                     ~ ~ ~


 6. CONFIGURA��O OP��ES

 O seguinte � uma lista de vari�veis encontradas no "phpmussel.ini"
 configura��o arquivo de phpMussel, juntamente com uma descri��o de sua
 prop�sito e fun��o.

 "general" (Categoria)
 - Geral configura��o por phpMussel.
    "script_password"
    - Como uma conveni�ncia, phpMussel permitir�s certas fun��es (incluindo a
      capacidade de atualizando phpMussel remotamente) ao ser acionado
      manualmente atrav�s de POST, GET e QUERY. Mas, como medida de seguran�a,
      para fazer isso, phpMussel esperam uma senha para ser inclu�da com o
      comando, forma a garantir que � voc�, e n�o outra pessoa, tentando de
      acionar manualmente essas fun��es. Definir script_password para qualquer
      senha que voc� desej� usar. Se nenhuma senha for definida, o manual
      acionamento ser� desativado por padr�o. Uso algo que voc� vai se lembrar,
      mas que � dif�cil por outros adivinharem.
      * N�o tem influ�ncia em CLI modo.
    "logs_password"
    - O mesmo como script_password, mas por visualizando conte�do de scan_log e
      scan_kills. Tendo separadas senhas pode ser �til se voc� quiser dar
      algu�m o acesso a um conjunto de fun��es mas n�o o outro.
      * N�o tem influ�ncia em CLI modo.
    "cleanup"
    - Deletar script vari�veis e cache ap�s a execu��o. Se voc� n�o estiver
      usar o script al�m da inicial verifica��o de carregamentos, deve definir
      a sim/yes, para minimizar o uso de mem�ria. Se voc� estiver usar o script
      por fins al�m da inicial verifica��o de carregamentos, deve definir a
      n�o/no, para evitar desnecessariamente duplicados dados recarregando em
      mem�ria. Em pr�tica geral, deve provavelmente ser definido como sim/yes,
      mas, se voc� fizer isso, voc� n�o ser� capaz de usando o script por
      qualquer outra fim al�m analisando arquivos carregamentos.
      * N�o tem influ�ncia em CLI modo.
    "scan_log"
    - Arquivo nome do arquivo para registrar todos os an�lise resultados em.
      Especifique um arquivo nome, ou deixe branco para desativar.
    "scan_kills"
    - Arquivo nome do arquivo para registrar todos os bloqueados ou matados
      carregamentos em. Especifique um arquivo nome, ou deixe branco para
      desativar.
    "ipaddr"
    - Onde encontrar o IP endere�o dos pedidos? (�til por servi�os como o
      Cloudflare e tal) Padr�o = REMOTE_ADDR
      ATEN��O: N�o mude isso a menos que voc� saiba o que est� fazendo!
    "forbid_on_block"
    - Deve phpMussel enviar 403 header com a bloqueado arquivo carregamento
      mensagem, ou ficar com os habituais 200 OK?
      0 = N�o (200) [Padr�o], 1 Sim (403).
    "delete_on_sight"
    - Ativando esta op��o ir� instruir o script para tentar imediatamente
      deletando qualquer arquivo que ele encontra durante a an�lise que
      corresponde a qualquer crit�rio de detec��o, quer seja atrav�s de
      assinaturas ou de outra forma. Arquivos determinados para ser "limpo" n�o
      ser�o tocados. Em caso de compactados arquivos, o inteiro arquivo ser�
      deletado (independentemente de se o problem�tico arquivo � apenas um dos
      v�rios arquivos contidos dentro do compactado arquivo). Para o caso de
      arquivo carregamento an�lise, em geral, n�o � necess�rio ativar essa
      op��o, porque normalmente, php ir� automaticamente expurgar os conte�dos
      de o seu cache quando a execu��o foi conclu�da, significando que ele vai
      normalmente deletar todos os arquivos enviados atrav�s dele para o
      servidor a menos que tenha movido, copiado ou deletado j�. A op��o �
      adicionado aqui como uma medida de seguran�a para o extra paran�ico e por
      aqueles cujas c�pias de php nem sempre se comportam da forma esperado.
      0 - Ap�s a an�lise, deixe o arquivo sozinho [Padr�o],
      1 - Ap�s a an�lise, se n�o limpo, deletar imediatamente.
    "lang"
    - Especifique o padr�o l�ngua por phpMussel.
    "quarantine_key"
    - phpMussel � capaz de colocar em quarentena marcados tentados arquivos
      carregamentos em isolamento dentro da phpMussel vault, se isso � algo que
      voc� quer que ele fa�a. Casuais usu�rios de phpMussel de que simplesmente
      desejam proteger seus sites ou hospedagem sem ter qualquer interesse em
      profundamente analisando qualquer marcados tentados arquivos
      carregamentos deve deixar esta funcionalidade desativada, mas qualquer
      usu�rio interessado em mais profundamente analisando marcados tentados
      arquivos carregamentos para pesquisa de malware ou de similares tais
      coisas deve ativada essa funcionalidade. Quarentena de marcados tentados
      arquivos carregamentos �s vezes pode tamb�m ajudar em depura��o de
      falso-positivos, se isso � algo que ocorre com freq��ncia para voc�. Por
      desativar a funcionalidade de quarentena, simplesmente deixar a directiva
      "quarantine_key" vazio, ou apagar o conte�do do directivo, se ele n�o
      est� j� vazio. Por ativar a funcionalidade de quarentena, introduzir
      algum valor no directiva. O "quarantine_key" � um importante seguran�a
      caracter�stica do quarentena funcionalidade necess�ria como um meio de
      prevenir a funcionalidade de quarentena de ser explorada por potenciais
      atacantes e como meio de evitar qualquer potencial execu��o de dados
      armazenados dentro da quarentena. O "quarantine_key" devem ser tratados
      da mesma maneira como suas senhas: O mais longo o mais melhor, e
      guard�-lo com for�a. Por melhor efeito, usar em conjunto com
      "delete_on_sight".
    "quarantine_max_filesize"
    - O m�ximo permitido tamanho do arquivos serem colocados em quarentena.
      Arquivos maiores que este valor N�O ser�o colocados em quarentena. Esta
      directiva � importante como um meio de torn�-lo mais dif�cil por qualquer
      potenciais atacante para inundar sua quarentena com indesejados dados
      potencialmente causando excesso uso de dados no seu hospedagem servi�o.
      O valor � em KB. Padr�o =2048 =2048KB =2MB.
    "quarantine_max_usage"
    - O m�ximo uso de mem�ria permitido atrav�s do quarentena. Se o total de
      mem�ria utilizada pelo quarentena atingir este valor, os mais antigos
      arquivos em quarentena ser�o apagados at� que a total mem�ria utilizada
      j� n�o atinge este valor. Esta directiva � importante como um meio de
      torn�-lo mais dif�cil por qualquer potenciais atacante para inundar sua
      quarentena com indesejados dados potencialmente causando excesso uso de
      dados no seu hospedagem servi�o. O valor � em KB.
      Padr�o =65536 =65536KB =64MB.
    "honeypot_mode"
    - Quando o honeypot modo � ativada, phpMussel vai tenta coloca no
      quarentena todos os arquivos uploads que ele encontras, independentemente
      de se ou n�o o arquivo que est� sendo carregado corresponde a qualquer
      inclu�dos assinaturas, e zero an�lise desses tentados arquivos
      carregamentos vai ocorrer. Esta funcionalidade deve ser �til por aqueles
      que desejam utilizar phpMussel por os fins de v�rus/malware pesquisa, mas
      n�o � recomendado para ativar essa funcionalidade se o planejado uso de
      phpMussel pelo utilizador � por o real an�lise dos arquivos carregamentos
      nem recomendado para usar essa funcionalidade por fins outros que o uso
      do honeypot. Por padr�o, essa op��o est� desativada.
      0 = Desativado [Padr�o], 1 = Ativado.
 "Assinaturas" (Categoria)
 - Configura��o por assinaturas.
   %%%_clamav = ClamAV assinaturas (ambos main e daily).
   %%%_custom = Suas personalizadas assinaturas (se voc� escrever alguma).
   %%%_mussel = phpMussel assinaturas inclu�do no seus atuais assinaturas
                conjunto que n�o s�o do ClamAV.
   - Verificar contra MD5 assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Verificar contra geral assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Verificar contra normalizada ASCII assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - Verificar contra normalizada HTML assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - Verificar PE (Port�til Execut�vel) arquivos (EXE, DLL, etc) contra PE
     Seccional assinaturas quando analisando? 0 = N�o, 1 = Sim [Padr�o].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Verificar PE (Port�til Execut�vel) arquivos (EXE, DLL, etc) contra PE
     assinaturas quando analisando? 0 = N�o, 1 = Sim [Padr�o].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Verificar ELF arquivos contra ELF assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Verificar Mach-O arquivos (OSX, etc) contra Mach-O assinaturas quando
     analisando? 0 = N�o, 1 = Sim [Padr�o].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Verificar gr�ficos arquivos contra gr�ficas assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Verificar compactados arquivos conte�do contra compactados arquivos
     metadados assinaturas quando analisando? 0 = N�o, 1 = Sim [Padr�o].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Verificar OLE objetos contra OLE assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - Verificar arquivos nomes contra assinaturas arquivos nomes baseadas
     assinaturas quando analisando? 0 = N�o, 1 = Sim [Padr�o].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Permitir an�lise com phpMussel_mail()? 0 = N�o, 1 = Sim [Padr�o].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Habilite arquivo-espec�fico whitelist? 0 = N�o, 1 = Sim [Padr�o].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - Verificar XML/XDP peda�os contra XML/XDP-peda�o assinaturas quando
     analisando? 0 = N�o, 1 = Sim [Padr�o].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - Verificar contra Complexos Estendidos assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - Verificar contra PDF assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - Verificar contra Shockwave assinaturas quando analisando?
     0 = N�o, 1 = Sim [Padr�o].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Assinatura analisando comprimento limitando op��es. Apenas alterar estes
     se voc� sabe que est� fazendo. SD = Standard signatures (norma
     assinaturas). RX = PCRE (Perl Compatible Regular Expressions, ou "Regex")
     assinaturas. FN = Arquivo nome assinaturas. Se voc� notar php falhando
     quando phpMussel tenta analisar, tente diminuir o "max" valores. Se
     poss�vel e conveniente, deixe-me saber quando isso acontece e os
     resultados de tudo o que voc� tentar.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Deve phpMussel reportar quando os assinaturas arquivos est�o perdido ou
     corrompido? Se fail_silently est� desativado, perdidos e corrompidos
     arquivos ser�o reportado sobre an�lise, e se fail_silently est� ativado,
     perdidos e corrompidos arquivos ser�o ignoradas, com a an�lise reportado
     por estes arquivos em que n�o h� problemas. Isso geralmente deve ser
     deixado sozinho a menos que voc� est� experimentando php falhas ou
     semelhantes problemas. 0 = Desativado [Padr�o], 1 = Ativado.
     "fail_silently"
 "files" (Categoria)
 - Geral configura��o por a manipula��o de arquivos.
   "max_uploads"
   - O m�ximo permitido n�mero de arquivos para analisar durante os arquivos
     carregamentos an�lise antes de abortar a an�lise e informando ao usu�rio
     eles est�o carregando demais muito de uma vez! Oferece prote��o contra um
     te�rico ataque pelo qual um atacante tenta DDoS o seu sistema ou CMS por
     meio de sobrecarregando phpMussel a fim de retardar o php processo para
     uma parada. Recomendado: 10. Voc� pode querer aumentar ou diminuir esse
     n�mero, dependendo das atributos do seu hardware. Note-se que este n�mero
     n�o lev. Em conta ou incluir o conte�dos dos compactados arquivos.
   "filesize_limit"
   - Arquivo tamanho limit. Em KB. 65536 = 64MB [Padr�o]
     0 = N�o limite (sempre greylisted), qualquer (positivo) num�rico valor
     aceite. Isso pode ser �til quando sua PHP configura��o limita a quantidade
     de mem�ria que um processo pode ocupar ou se sua PHP configura��o limita o
     arquivo tamanho de carregamentos.
   "filesize_response"
   - Que fazer com arquivos que excedam o limite de arquivo tamanho (se
     existir). 0 - Whitelist, 1 - Blacklist [Padr�o].
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - Se o seu sistema s� permite certos tipos de arquivos sejam carregado, ou
     se o seu sistema explicitamente nega certos tipos de arquivos,
     especificando esses tipos de arquivos no whitelists, blacklists e
     greylists pode aumentar a velocidado em que a an�lise � realizada atrav�s
     de permitindo o script para ignorar certos tipos de arquivos. O formato
     CSV (Comma Separated Values). Se voc� quer analisar tudo, ao inv�s de
     fazendo whitelist, blacklist ou greylist, deixe as vari�veis em branco;
     Isso ir� desativar whitelist/blacklist/greylist).
     L�gico ordem de processamento �:
     - Se o tipo de arquivo est� na whitelist, n�o verificar e n�o bloqueia o
       arquivo, e n�o verificar o arquivo contra o blacklist ou greylist.
     - Se o tipo de arquivo est� na blacklist, n�o verificar o arquivo, mas
       bloque�-lo de qualquer maneira, e n�o verificar o arquivo contra o
       greylist.
     - Se o greylist est� vazia ou se o greylist n�o est� vazia e o tipo de
       arquivo � no greylist, verificar o arquivo como por normal e determinar
       se a bloque�-lo com base nos resultados do verificando, mas se o
       greylist n�o est� vazia e o tipo de arquivo n�o � no greylist, tratar o
       arquivo da mesma maneira como est� na blacklist, portanto n�o
       verific�-lo, mas bloque�-lo de qualquer maneira.
   "check_archives"
   - Tentativa de verificar o conte�dos dos compactados arquivos?
     0 - N�o (N�o verificar), 1 - Sim (Verificar) [Padr�o].
     * Neste momento, apenas a verifica��o de BZ, GZ, LZF e ZIP arquivos �
       suportados (verifica��o de RAR, CAB, 7z e etcetera suportados neste
       momento).
     * Este n�o � infal�vel! Embora eu recomendo mant�-lo ativado, eu n�o posso
       garantir que sempre vai encontrar tudo.
     * Tamb�m estar ciente de que a verifica��o do compactados arquivos, neste
       momento, n�o � recursiva por ZIP arquivos.
   "filesize_archives"
   - Herdar o arquivo tamanho blacklist/whitelist para o conte�do de
     compactados arquivos? 0 - N�o (greylist tudo), 1 - Sim [Padr�o].
   "filetype_archives"
   - Herdar o arquivo tipo blacklist/whitelist para o conte�do de compactados
     arquivos? 0 - N�o (greylist tudo), 1 - Sim [Padr�o].
   "max_recursion"
   - M�xima recurs�o profundidade limite por compactados arquivos. Padr�o = 10.
 "attack_specific" (Categoria)
 - Configura��o por espec�ficas ataque detec��es (n�o baseado em CVDs).
   * Chameleon ataque detec��es: 0 = Ativo, 1 = Inativo.
   "chameleon_from_php"
   - Olha por php heade. Em arquivos que s�o n�o php arquivos nem
     reconhecidos compactados arquivos.
   "chameleon_from_exe"
   - Olha por execut�vel headers em arquivos que s�o n�o execut�veis nem
     reconhecidos compactados arquivos e por execut�veis cujos headers est�o
     incorretas.
   "chameleon_to_archive"
   - Olha por compactados arquivos cujos headers est�o incorretas
     (Suportados: BZ, GZ, RAR, ZIP, RAR, GZ).
   "chameleon_to_doc"
   - Olha por office documentos cujos headers est�o incorretas
     (Suportados: DOC, DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Olha por imagens cujos headers est�o incorretas (Suportados: BMP, DIB,
     PNG, GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Olha por PDF arquivos cujos headers est�o incorretas.
   "archive_file_extensions" and "archive_file_extensions_wc"
   - Reconhecidos arquivos extens�es (formato � CSV; s� deve adicionar ou
     remover quando problemas ocorrem; desnecessariamente removendo pode causar
     falso-positivos para aparecer por compactados arquivos, enquanto
     desnecessariamente adicionando ser� essencialmente whitelist o que voc�
     est� adicionando contra ataque espec�fica detec��o; modificar com cautela;
     Tamb�m notar que este n�o tem efeito em qual compactados arquivos podem e
     n�o podem ser analisados no escopo de conte�do). A lista, como � padr�o,
     � do formatos utilizados mais comumente atrav�s da maioria dos sistemas e
     CMS, mas intencionalmente n�o � necessariamente abrangente.
   "general_commands"
   - Olha por gerais comandos como tais eval(), exec() e include() em conte�dos
     de arquivos? 0 - N�o (n�o olha por) [Padr�o], 1 - Sim (olha por).
     Desativar essa op��o se voc� s�o tencionando de carregando qualquer um do
     seguinte para o seu sistema ou CMS atrav�s do seu navegador: php,
     JavaScript, HTML, python, perl files e etcetera. Ativar essa op��o se voc�
     n�o tem quaisquer adicionais prote��es no seu sistema e n�o s�o
     tencionando de carregando desses tais arquivos. Se voc� usar adicional
     seguran�a em conjunto com phpMussel como ZB Block, n�o h� necessidade de
     activar esta op��o, porque a maioria dos que phpMussel ir� olha por (no
     contexto desta op��o) s�o duplica��es de prote��es que j� est�o fornecida.
   "block_control_characters"
   - Bloquear todos os arquivos que contenham quaisquer controle caracteres
     (exceto linha quebras) - [\x00-\x08\x0b\x0c\x0e\x1f\x7f]? Se voc� est�
     -apenas- carregando simple texto, ent�o voc� pode ativar essa op��o para
     fornecer alguma adicional prote��o para o seu sistema. Mas, se voc�
     carregar qualquer coisa que n�o seja de texto simples, ativando isso pode
     resultas em falso positivos. 0 - N�o bloquear [Padr�o], 1 - Bloquear.
   "corrupted_exe"
   - Corrompidos arquivos e erros de an�lise.
     0 = Ignorar, 1 = Bloquear [Padr�o]. Detectar e bloquear potencialmente
     corrompidos PE (Port�til Execut�vel) arquivos? Often (but not always),
     quando certos aspectos de um PE arquivo � corrompido ou n�o pode ser
     analisado corretamente, essa pode ser indicativo de uma viral infec��o. Os
     processos utilizados pela maioria dos anti-v�rus programas para detectar
     v�rus em PE arquivos requerem analisando os arquivos de certas maneiras,
     que, se o programador de um v�rus � consciente de, especificamente ir�
     tentar impedir, a fim de permitir seu v�rus para permanecer n�o detectado.
   "decode_threshold"
   - Opcional limita��o para o comprimento dos brutos dados para que dentro de
     decodificar comandos devem ser detectados (em caso de existirem quaisquer
     not�vel problemas de desempenho enquanto analisando). Valor � um inteiro
     que representa tamanho do arquivo Em KB. Padr�o = 512 (512KB). Zero ou
     nulo valor desativa o limita��o (removendo qualquer limita��o baseado em
     tamanho do arquivo).
   "scannable_threshold"
   - Opcional limita��o para o comprimento dos brutos dados para que phpMussel
     � permitido a ler e analisar (em caso de existirem quaisquer not�vel
     problemas de desempenho enquanto analisando). Valor � um inteiro que
     representa tamanho do arquivo Em KB. Padr�o = 32768 (32MB). Zero ou nulo
     valor desativa o limita��o. Em geral, esse valor n�o deve ser menor que o
     m�dio arquivo tamanho de carregamentos que voc� quer e espera para receber
     no seu servidor ou website, n�o deve ser mais que o filesize_limit
     directivo, e n�o deve ser menor que aproximadamente um quinto do total
     permiss�vel mem�ria aloca��o concedido para php atrav�s do php.ini
     configura��o arquivo. Esta directiva existe para tentar impedir phpMussel
     de usando demais mem�ria (que seria impedir-lo de ser capaz de analisando
     arquivos acima de um certo tamanho com sucesso).
 "compatibility" (Categoria)
 - Compatibilidade directivas por phpMussel.
   "ignore_upload_errors"
   - Essa directiva deve ser geralmente desativada a menos que seja necess�rio
     por correta funcionalidade de phpMussel no seu espec�fico sistema.
     Normalmente, quando desativado, quando phpMussel detecta a presen�a de
     elementos dentro a $_FILES array(), ele tentar� iniciar uma an�lise dos
     arquivos que esses elementos representam, e, se esses elementos est�o
     branco ou vazia, phpMussel ir� retornar uma erro mensagem. Esse � um
     apropriado comportamento por phpMussel. Mas, por alguns CMS, vazios
     elementos podem ocorrer como resultado do natural comportamento dessas
     CMS, ou erros podem ser reportado quando n�o houver alguma, nesse caso, o
     normal comportamento por phpMussel ser� interferindo com o normal
     comportamento dessas CMS. Se tal situa��o ocorre por voc�, ativando esta
     op��o ir� instruir phpMussel para n�o tentar iniciar um an�lise por tais
     vazios elementos, ignor�-los quando encontrado e para n�o retornar
     qualquer relacionado erro mensagens, assim, permitindo a continua��o da
     p�gina carga. 0 - DESATIVADO, 1 - ATIVADO.
   "only_allow_images"
   - Se voc� apenas esperar ou apenas tencionar de permitir imagens a ser
     enviado para seu sistema ou CMS, e se voc� absolutamente n�o necessita
     quaisquer arquivos exceto imagens a ser enviado para seu sistema ou CMS,
     esta directiva devia ser ATIVADO, mas em outros casos devia ser
     DESATIVADO. Se esta diretiva � ATIVADO, ele ir� instruir phpMussel
     indiscriminadamente bloquear qualquer arquivo carregamento identificado
     como n�o imagem, sem os analisar. Isto pode reduzir o tempo de
     processamento e uso de mem�ria por tentados carregamentos de n�o imagem
     arquivos. 0 - DESATIVADO, 1 - ATIVADO.

                                     ~ ~ ~


 7. ASSINATURA FORMATO

 = ARQUIVO NOME ASSINATURAS =
   Todas as arquivo nome assinaturas seguir o formato:
    NAME:FNRX
   Onde NAME � o nome para citar por essa assinatura e FNRX � o regex para
   verificar arquivos nomes (n�o codificados) contra.

 = MD5 ASSINATURAS =
   Todas as MD5 assinaturas seguir o formato:
    HASH:FILESIZE:NAME
   Onde HASH � o MD5 hash de um inteiro arquivo, FILESIZE � o total tamanho do
   arquivo e NAME � o nome para citar por essa assinatura.

 = COMPACTADOS ARQUIVOS METADADOS ASSINATURAS =
   Todas as compactados arquivos metadados assinaturas seguir o formato:
    NAME:FILESIZE:CRC32
   Onde NAME � o nome para citar por essa assinatura, FILESIZE � o total
   tamanho (descompactado) de um arquivo contido dentro do compactado arquivo e
   CRC32 � o CRC32 checksum do contido arquivo.

 = PE SECCIONAL MD5 ASSINATURAS =
   Todas as PE Seccional MD5 assinaturas seguir o formato:
    FILESIZE:HASH:NAME
   Onde HASH � o MD5 hash de uma sec��o do PE arquivo, FILESIZE � o total
   tamanho do arquivo e NAME � o nome para citar por essa assinatura.

 = WHITELIST ASSINATURAS =
   Todas as Whitelist assinaturas seguir o formato:
    HASH:FILESIZE:TYPE
   Onde HASH � o MD5 hash de um inteiro arquivo, FILESIZE � o total tamanho do
   arquivo e NAME � o nome para citar por essa assinatura.
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size
   of that file and TYPE � o tipo de assinaturas do whitelist arquivo � ser
   imune contra.

 = COMPLEXOS ESTENDIDOS ASSINATURAS =
   Complexos Estendidos assinaturas s�o bastante diferente para os outros tipos
   de assinaturas poss�veis com phpMussel em que o que eles est�o verificando
   contra � especificado pelas assinaturas e eles podem verificar contra v�rios
   crit�rios. Os crit�rios de verifica��o s�o delimitados por ";" e o
   verifica��o tipo e os verifica��o dados de cada verifica��o crit�rios �
   delimitados por ":" como assim que o formato por estas assinaturas tende a
   olhar um pouco assim:
    $vari�vel1:ALGUNSDADOS;$vari�vel2:ALGUNSDADOS;AssinaturaNome

 = TODAS OUTRAS =
   Todas as outras assinaturas seguir o formato:
    NAME:HEX:FROM:TO
   Onde NAME � o nome para citar por essa assinatura e HEX � um hexadecimal
   codificado segmento do arquivo intentado a ser correspondido pela dado
   assinatura. TO e FROM s�o opcionais par�metros, indicando de onde e para
   quais posi��es nos origem dados para verificar contra (n�o suportado pela
   mail fun��o).

 = REGEX =
   Qualquer forma de regex compreendido e processado corretamente pelo php
   tamb�m deve ser correctamente compreendido e processado por phpMussel e suas
   assinaturas. Mas, eu sugiro tomar extremo cuidado quando escrevendo novas
   assinaturas baseadas regex, porque, se voc� n�o est� inteiramente certo do
   que est� fazendo, isto pode tem altamente irregulares e inesperadas
   resultados. Olha para o c�digo-fonte de phpMussel Se voc� n�o est�
   totalmente certo sobre o contexto em que as regex declara��es s�o
   processada. Al�m, lembre-se que todos isso (com exce��o para arquivo nome,
   compactado arquivo metadados, MD5 a sintaxe) deve ser codificado
   hexadecimalmente!

 = ONDE COLOCAR PERSONALIZADAS ASSINATURAS? =
   Colocar personalizadas assinaturas nos arquivos destinado por personalizadas
   assinaturas s�. Esses arquivos devem conter "_custom" no seus nomes. Voc�
   tamb�m deve evitar editando padr�o assinatura arquivos, a menos que voc�
   sabe exatamente o que voc� est� fazendo, por raz�o que, al�m de sendo boa
   pr�tica em geral e al�m de ajud�-lo distinguir entre suas pr�prias
   assinaturas e as padr�os assinaturas inclu�dos com phpMussel, � bom para
   manter para editando apenas os arquivos destinados por editando, por raz�o
   de que mexendo com os padr�o assinatura arquivos pode caus�-los a cessar
   funcionando corretamente, devido aos "mapas" arquivos: Os mapas arquivos
   instruir phpMussel onde nos assinatura arquivos para olhar por assinaturas
   necess�rio por phpMussel tal quando necess�rio, e esses mapas podem
   tornar-se fora de sincronia com seus associadas assinatura arquivos se esses
   assinatura arquivos s�o adulterado com. Voc� pode essencialmente colocar
   qualquer voc� quiser no seus personalizadas assinaturas, desde que voc� siga
   a correta sintaxe. Mas, cuidado para testar novas assinaturas por
   falso-positivos de antem�o se voc� tencionar de compartilh�-los ou us�-los
   em um ambiente vivo.

 = ASSINATURA COMPOSI��O =
   A seguir est�o os diferentes tipos de assinaturas utilizadas por phpMussel:
   - "Normalizadas ASCII Assinaturas" (ascii_*). Verificado contra o conte�do
      de cada arquivo n�o no whitelist e alvo por analisando.
   - "Estendidos Complexos Assinaturas" (coex_*). misto tipo de assinatura
      verificando.
   - "ELF Assinaturas" (elf_*). Verificado contra o conte�do de cada arquivo
      n�o no whitelist e alvo por analisando e confirmados tal do formato ELF.
   - "Port�til Execut�vel Assinaturas" (exe_*). Verificado contra o conte�do de
      cada arquivo n�o no whitelist e alvo por analisando e confirmados tal do
      formato PE.
   - "Arquivo Nome Assinaturas" (filenames_*). Verificado contra os nomes de
      cada arquivo n�o no whitelist e alvo por analisando.
   - "Gerais Assinaturas" (general_*). Verificado contra o conte�do de arquivo
      n�o no whitelist e alvo por analisando.
   - "Gr�ficas Assinaturas" (graphics_*). Verificado contra o conte�do de cada
      arquivo n�o no whitelist e alvo por analisando e confirmado tal de um
      conhecidos gr�ficos arquivos formato.
   - "Gerais Comandos" (hex_general_commands.csv). Verificado contra o conte�do
      de cada arquivo n�o no whitelist e alvo por analisando.
   - "Normalizadas HTML Assinaturas" (html_*). Verificado contra o conte�do de
      cada arquivo n�o no whitelist e alvo por analisando.
   - "Mach-O Assinaturas" (macho_*). Verificado contra o conte�do de cada
      arquivo n�o no whitelist e alvo por analisando e confirmados tal do
      formato Mach-O.
   - "E-mail Assinaturas" (mail_*). Verificado contra o $body vari�vel
      alimentado para o phpMussel_mail() fun��o, que se intencionado para ser o
      corpo das e-mail mensagens ou similares entidades (potencialmente f�rum
      mensagens e etcetera).
   - "MD5 Assinaturas" (md5_*). Verificado contra o MD5 hash do conte�do e
      contra o arquivo tamanho de cada arquivo n�o no whitelist e alvo por
      analisando.
   - "Compactado Arquivo Metadado Assinaturas" (metadata_*). Verificado contra
      o CRC32 hash eo arquivo tamanho do inicial arquivo contida dentro de cada
      compactado arquivo n�o no whitelist e alvo por analisando.
   - "OLE Assinaturas" (ole_*). Verificado contra o conte�do de cada objeto n�o
      no whitelist e alvo por analisando.
   - "PDF Assinaturas" (pdf_*). Verificado contra o conte�do de cada PDF
      arquivo n�o no whitelist.
   - "Port�til Execut�vel Seccional Assinaturas" (pe_*). Verificado contra o
      tamanho eo MD5 hash de cada PE se��o de cada arquivo n�o em o whitelist e
      alvo por analisando e confirmados tal do formato PE.
   - "SWF Assinaturas" (swf_*). Verificado contra o conte�do de cada Shockwave
      arquivo n�o no whitelist.
   - "Whitelist Assinaturas" (whitelist_*). Verificado contra o MD5 hash do
      conte�do e contra o arquivo tamanho de cada arquivo alvo por analisando.
      Verificados arquivos ser� imune de sendo verificado pelo tipo de
      assinatura mencionada no seu whitelist entrada.
   - "XML/XDP-Peda�o Assinaturas" (xmlxdp_*). Verificado contra quaisquer
      XML/XDP peda�os encontrados dentro cada arquivo n�o no whitelist e alvo
      por analisando.
     (Notar que qualquer uma destas assinaturas podem ser facilmente desativada
      atrav�s de phpmussel.ini).

                                     ~ ~ ~


 8. CONHECIDOS COMPATIBILIDADE PROBLEMAS

 PHP e PCRE
 - phpMussel requer PHP e PCRE para executar e funcionar corretamente. Sem PHP,
   ou sem a PCRE extens�o do PHP, phpMussel n�o vai executar� ou funcionar
   corretamente. Deve certificar-se de que seu sistema tenha PHP e PCRE
   instalado e dispon�vel antes de baixar e instalar phpMussel.

 ANTI-V�RUS SOFTWARE COMPATIBILIDADE

 Em geral, phpMussel deve ser bastante compat�vel com a maioria dos outros
 v�rus detec��o softwares. Embora, conflitos foram relatadas por um n�mero de
 utilizadores no passado. Esta informa��o abaixo � de VirusTotal.com, e
 descreve um n�mero de falso-positivos relatados por v�rios anti-v�rus
 programas contra phpMussel. Embora esta informa��o n�o � um absoluta garantia
 de haver ou n�o voc� vai encontrar problemas de compatibilidade entre
 phpMussel e seu anti-v�rus software, se o seu anti-v�rus software � conhecido
 como sinaliza��o contra phpMussel, voc� deve considerar desativ�-lo antes de
 trabalhar com phpMussel ou deve considerar alternativas op��es para o seu
 anti-v�rus software ou phpMussel.

 Esta informa��o foi atualizada dia 4 Fevereiro 2015 e � corrente para todas
 phpMussel lan�amentos das duas mais recentes menores vers�es (v0.5-v0.6) no
 momento de escrever este.

 Ad-Aware                Sem conhecidos problemas
 Agnitum                 Sem conhecidos problemas
 AhnLab-V3               Sem conhecidos problemas
 AntiVir                 Sem conhecidos problemas
 Antiy-AVL               Sem conhecidos problemas
 Avast                !  Reportar "JS:ScriptSH-inf [Trj]"
 AVG                     Sem conhecidos problemas
 Baidu-International     Sem conhecidos problemas
 BitDefender             Sem conhecidos problemas
 Bkav                    Sem conhecidos problemas
 ByteHero                Sem conhecidos problemas
 CAT-QuickHeal           Sem conhecidos problemas
 ClamAV                  Sem conhecidos problemas
 CMC                     Sem conhecidos problemas
 Commtouch               Sem conhecidos problemas
 Comodo                  Sem conhecidos problemas
 DrWeb                   Sem conhecidos problemas
 Emsisoft                Sem conhecidos problemas
 ESET-NOD32              Sem conhecidos problemas
 F-Prot                  Sem conhecidos problemas
 F-Secure                Sem conhecidos problemas
 Fortinet                Sem conhecidos problemas
 GData                   Sem conhecidos problemas
 Ikarus                  Sem conhecidos problemas
 Jiangmin                Sem conhecidos problemas
 K7AntiVirus             Sem conhecidos problemas
 K7GW                    Sem conhecidos problemas
 Kaspersky               Sem conhecidos problemas
 Kingsoft                Sem conhecidos problemas
 Malwarebytes            Sem conhecidos problemas
 McAfee               !  Reportar "New Script.c"
 McAfee-GW-Edition    !  Reportar "New Script.c"
 Microsoft               Sem conhecidos problemas
 MicroWorld-eScan        Sem conhecidos problemas
 NANO-Antivirus          Sem conhecidos problemas
 Norman               !  Reportar "Kryptik.BQS"
 nProtect                Sem conhecidos problemas
 Panda                   Sem conhecidos problemas
 Qihoo-360               Sem conhecidos problemas
 Rising                  Sem conhecidos problemas
 Sophos                  Sem conhecidos problemas
 SUPERAntiSpyware        Sem conhecidos problemas
 Symantec             !  Reportar "WS.Reputation.1"
 TheHacker               Sem conhecidos problemas
 TotalDefense            Sem conhecidos problemas
 TrendMicro              Sem conhecidos problemas
 TrendMicro-HouseCall    Sem conhecidos problemas
 VBA32                   Sem conhecidos problemas
 VIPRE                   Sem conhecidos problemas
 ViRobot                 Sem conhecidos problemas


                                     ~ ~ ~


�ltima Atualiza��o: 3 Mar�o 2015 (2015.03.03).
EOF
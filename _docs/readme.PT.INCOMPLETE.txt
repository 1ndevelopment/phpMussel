      _____  _     _  _____  _______ _     _ _______ _______ _______           
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____    

                           { ~ ~ ~ PORTUGU�S ~ ~ ~ }                           
    Obrigado por usando phpMussel, um script baseado em php baseado em ClamAV  
  assinaturas projetado para detectar trojans, v�rus, malware e outras amea�as 
    dentro arquivos uploaded para seu sistema sempre que script � enganchado.  
   PHPMUSSEL COPYRIGHT 2013 e al�m GNU/GPL V.2 atrav�s do Caleb M (Maikuolan)  

                                     ~ ~ ~                                     


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

 Um agradecimento especial a ClamAV tanto para o projeto inspira��o e para as  
 assinaturas que este script utiliza, sem que, o script provavelmente n�o      
 existiria, ou em o melhor, teria ser de muito limitado valor.                 
 <http://www.clamav.net/lang/en/>                                              

                                     ~ ~ ~                                     
 Este script � livre software; voc� pode redistribu�-lo e/ou modific�-lo de    
 acordo com os termos da GNU General Public License como publicada pela Free   
 Software Foundation; tanto a vers�o 2 da Licen�a, ou (em sua op��o) qualquer  
 vers�o posterior. Este script � distribu�do na esperan�a que possa ser �til,  
 mas SEM QUALQUER GARANTIA; sem mesmo a impl�cita garantia de COMERCIALIZA��O  
 ou ADEQUA��O A UM DETERMINADO FIM. Consulte a GNU General Public License para 
 obter mais detalhes. <http://www.gnu.org/licenses/>                           
 <http://opensource.org/licenses/>                                             

                                     ~ ~ ~                                     
 Este documento e seu associado pacote pode ser baixado gratuitamente a partir
 do Sourceforge. <http://sourceforge.net/projects/phpmussel/>

                                     ~ ~ ~                                     


 2A. COMO INSTALAR (PARA WEB SERVIDORES)

 Espero para agilizar este processo via fazendo um instalador em algum momento
 no n�o muito distante futuro, mas at� ent�o, siga estas instru��es para
 trabalhar phpMussel na maioria dos sistemas e CMS:

 1) Por seu lendo isso, eu estou supondo que voc� j� tenha baixado uma c�pia
    arquivada do script, descomprimido seu conte�do e t�-lo sentado em algum
    lugar em sua m�quina local. A partir daqui, voc� vai querer determinar onde
    em seu host ou CMS pretende colocar esses conte�dos. Um diret�rio como
    /public_html/phpmussel/ ou semelhante (no entanto, est� n�o importa qual
    voc� escolher, assumindo que � seguro e algo voc� esteja feliz com) vai
    bastar�.

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

 4) Fa�a o upload dos conte�dos (phpMussel e seus arquivos) para o diret�rio
    que voc� tinha decidido anteriormente (voc� n�o precisa o readme.XX.txt ou
    change_log.txt arquivos inclu�do, mas principalmente, voc� deve fazer o
    upload de tudo).

 5) CMHOD o "vault" diret�rio para "777". O principal diret�rio armazenar o
    conte�do (o que voc� escolheu anteriormente), geralmente, pode ser deixado
    sozinho, mas o CHMOD status deve ser verificado se voc� j� teve problemas
    de permiss�es no passado em seu sistema (por padr�o, deve ser algo como
    "755").

 6) Seguida, voc� vai precisar "enganchar" phpMussel ao seu sistema ou CMS.
    Existem v�rias diferentes maneiras em que voc� pode "enganchar" scripts
    como phpMussel ao seu sistema ou CMS, mas o mais f�cil � simplesmente
    incluir o script no in�cio de um n�cleo arquivo de seu sistema ou CMS (uma
    que vai geralmente sempre ser carregado quando algu�m acessa qualquer
    p�gina atrav�s de seu site) utilizando um require ou include comando.
    Normalmente, isso vai ser algo armazenados em um diret�rio como
    "/includes", "/assets" ou "/functions", e muitas vezes, ser nomeado algo
    como "init.php", "common_functions.php", "functions.php" ou semelhante.
    Voc� precisar� determinar qual arquivo isso � para a sua situa��o. Para
    fazer isso, insira a seguinte linha de c�digo para o in�cio desse n�cleo
    arquivo, substituindo a string contida dentro das aspas com o exato
    endere�o do "phpmussel.php" arquivo (endere�o local, n�o o endere�o HTTP;
    ser� semelhante ao vault endere�o mencionado anteriormente).

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Salve o arquivo, fechar, reupload.

 7) Neste ponto, voc� est� feito! No entanto, voc� provavelmente deve test�-lo
    para garantir que ele est� funcionando corretamente. Para testar as
    arquivos upload prote��es, tentar fazer o upload dos testes arquivos
    inclu�dos no pacote em "_testfiles" para seu site atrav�s de seus habitual
    navegador upload m�todos. Se tudo estiver funcionando, a mensagem deve
    aparecer a partir phpMussel confirmando que o upload foi bloqueado com
    sucesso. Se nada aparecer, algo est� n�o funcionando corretamente. Se voc�
    estiver usando quaisquer avan�ados recursos ou se voc� estiver usando
    outros tipos de an�lisar poss�vel com a ferramenta, Eu sugiro tentar isso
    com aqueles para certificar que ele funciona como esperado, tamb�m.

                                     ~ ~ ~                                     


 2B. COMO INSTALAR (PARA CLI)

 Espero para agilizar este processo via fazendo um instalador em algum momento
 no n�o muito distante futuro, mas at� ent�o, siga estas instru��es para obter
 phpMussel pronto para trabalhar com CLI (estar ciente, neste momento, CLI
 apoio s� se aplica a sistemas baseados no Windows; Linux e outros sistemas
 ser� em breve para uma posterior vers�o do phpMussel):

 1) Por seu lendo isso, eu estou supondo que voc� j� tenha baixado uma c�pia
    arquivada do script, descomprimido seu conte�do e t�-lo sentado em algum
    lugar em sua m�quina local. Quando voc� tiver determinado que voc� est�
    feliz com o localiza��o escolhido para phpMussel, continuar.

 2) phpMussel requer php para ser instalado na host m�quina a fim de executar.
    Se voc� n�o ainda tem o PHP instalado em sua m�quina, por favor instalar o
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
    instala��o, salvar o arquivo com a extens�o ".bat" em algum lugar que voc�
    vai encontr�-lo facilmente, e clique duas vezes nesse arquivo para executar
    phpMussel no futuro.

 6) Neste ponto, voc� est� feito! No entanto, voc� provavelmente deve test�-lo
    para garantir que ele est� funcionando corretamente. Para testar phpMussel,
    executar phpMussel e tente an�lizar o diret�rio "_testfiles" fornecida com
    o pacote.

                                     ~ ~ ~                                     


 3A. COMO USAR (PARA WEB SERVIDORES)

 phpMussel � um script destinado a funcionar de adequadamente, sem
 complica��es, com um m�nimo n�vel de requisitos por voc�: Ap�s ter sido
 instalado, basicamente, ele simplesmente deve funcionar.

 An�lise de arquivos uploads � automatizado e ativado por padr�o, por isso
 nada � exigido por voc� por essa particular fun��o.

 No entanto, voc� tamb�m � capaz de instruir phpMussel para analisar arquivos
 ou diret�rios que voc� especificar implicitamente. Para fazer isso, em
 primeiro lugar, voc� vai precisar para assegurar que apropriada configura��o �
 definida no phpmussel.ini arquivo (cleanup deve ser desativado), e quando
 feito, em um php arquivo que est� enganchado ao phpMussel, usar a seguinte
 fun��o no seu c�digo:

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
   resultados como humano leg�vel texto e para exportar os resultados para uma
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
    Wed, 18 Sep 2013 02:49:46 +0000 Come�ado.
    > Verifica��o '/user_name/public_html/my_file.html':
    -> N�o problemas encontrados.
    Wed, 18 Sep 2013 02:49:47 +0000 Terminado.

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

 Al�m da padr�o arquivos upload an�lise e a opcional an�lise de outros arquivos
 e/ou diret�rios especificado atrav�s da fun��o acima, inclu�do no phpMussel �
 uma fun��o destinada � an�lise do corpo das e-mail mensagens. Esta fun��o
 funciona da mesma forma para a phpMussel() fun��o, mas se concentra
 exclusivamente em fazer a compara��o com as assinaturas de ClamAV baseiam
 e-mail. Eu tenho amarrei essas assinaturas para a padr�o phpMussel() fun��o,
 porque � muito pouco prov�vel que voc� jamais encontrar o corpo de uma
 recebidos e-mail mensagem na necessidade de an�lise dentro um arquivo upload
 direcionados para uma p�gina onde phpMussel � enganchada, e assim, para
 amarrar essas assinaturas para a phpMussel() fun��o seria redundante. Mas, o
 que disse, tendo uma separada fun��o para comparar contra essas assinaturas
 poderia revelar-se extremamente �til para alguns, especialmente para aqueles
 cuja CMS ou webfront sistema est� de alguma modo enganchado em seu e-mail
 sistema e para aqueles de quem analisar seus e-mails atrav�s de um php script
 de que eles poderiam engancho para phpMussel. Configura��o para esta fun��o,
 como todos os outros, � controlado atr�ves do phpmussel.ini arquivo. Para
 utilizar esta fun��o (voc� vai precisar para fazer a sua pr�pria
 implementa��o), em um php arquivo que est� enganchado ao phpMussel, usar a
 seguinte fun��o no seu c�digo:

 phpMussel_mail($body);

 Onde $body � o corpo da email mensagem que voc� deseja analisar (Al�m, voc�
 pode tentar analisar novos f�rum posts, mensagens do seu on-line contato form
 ou similar). Se algum erro ocorrer impedindo a fun��o de completar a sua
 an�lise, um valor de -1 ser� retornado. Se a fun��o faz completa a sua an�lise
 e detecta nada, um valor de 0 ser� retornado (ou seja, limpo). Se, no entanto,
 a fun��o faz detectar algo, uma string ser� retornado contendo uma mensagem
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
 voc� tem configur� as vari�veis script_password e logs_password em seu
 configura��o arquivo, voc� ser� capaz de executar um limitado n�mero de
 administrativas fun��es e entrada um algum n�mero de comandos para phpMussel
 atrav�s de seu navegador. A raz�o pela qual essas senhas precisam ser
 definidas a fim de permitir que esses controles do navegador � tanto para
 garantir adequada seguran�a, adequada prote��o desses navegador controles e
 para garantir que existe um maneira por desses navegador controles para ser
 totalmente desativado se eles n�o s�o desejadas por voc� e/ou outros
 webmasters/administradores usando phpMussel. Portanto, em outras palavras,
 para ativar esses controles, definir uma senha, e para desativar esses
 controles, definir nenhum senha. Alternativamente, se voc� optar por ativar
 esses controles ent�o optar por desativar esses controles em uma posterior
 data, existe um comando para fazer isto (tal pode ser �til se voc� executar
 algumas a��es que voc� sente poderia comprometer as senhas delegados e precisa
 para desativar rapidamente esses controles sem modificar o configura��o
 arquivo).

 Algumas raz�es pelas quais voc� -deve- ativar esses controles:
 - Fornece uma maneira para greylist assinaturas em casos como quando voc�
   descobre uma assinatura que est� produzindo um falso-positivo enquanto o
   upload de arquivos para o seu sistema e voc� n�o tem tempo para manualmente
   editar e reupload o greylist arquivo.
 - Fornece uma maneira por voc� para permitir algu�m diferente de si mesmo para
   controlar a sua c�pia do phpMussel sem a impl�cita necessidade a dar o
   acesso ao FTP.
 - Fornece uma maneira de fornecer controlado acesso aos seus log arquivos.
 - Fornece uma f�cil maneira para atualizar phpMussel quando atualiza��es s�o
   dispon�veis.
 - Fornece uma maneira por voc� para monitorar phpMussel quando FTP acesso ou
   outras convencionais vias de acesso para monitoramento phpMussel n�o est�o
   dispon�veis.

 Algumas raz�es pelas quais voc� -n�o- deve ativar esses controles:
 - Fornece um vetor por potenciais atacantes e indesej�veis ??para determinar
   se ou n�o voc� est� usando phpMussel (embora, este poderia ser tanto uma
   raz�o por e uma raz�o contra, dependendo em perspectiva) por cegamente envio
   de comandos para os servidores como meio para sondar. Por um lado, isso pode
   desencorajar os atacantes de testando seu sistema, se eles descobrem que
   voc� est� usando phpMussel, assumindo que eles est�o sondando por raz�es que
   o sua m�todo de ataque � desprovido de efeito como resultado do seu uso de
   phpMussel. Mas, por outro lado, se algum imprevisto e presentemente
   desconhecidos vulnerabilidade dentro phpMussel ou uma futuro vers�o dos
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
            acontecer se voc� estiver usando esses controles a partir de um
            computador que n�o � seguro ou n�o � confi�vel). controls_lockout
            funciona atr�ves de criando um arquivo, controls.lck, em seu vault,
            de que phpMussel ir� olhar por antes de executar qualquer comando
            de qualquer variedade. Quando isso acontece, para reativar os
            controlos, voc� precisar� manualmente deletar o controls.lck
            arquivo atr�ves de FTP ou semelhante. Pode ser chamado usando
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
            quaisquer atualiza��es ou altera��es em seu sistema ou se est�
            instalando qualquer novo software ou m�dulos para o seu sistema que
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
            o processo, tal como atr�ves de cron ou semelhante. Eu recomendo
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

 Por uma lista de comandos dispon�veis em CLI, no CLI prompt, digite 'c', e
 pressione Enter.

                                     ~ ~ ~                                     


 5. ARQUIVOS INCLU�DOS NESTE PACOTE

 The following is a list of all of the files that should have been included
 in the archived copy of this script when you downloaded it, any files that may
 be potentially created as a result of your using this script, along with a
 short description of what all these files are for.

 /phpmussel.php (Script, Included)
    phpMussel Loader file. Loads the main script, updater, etcetera.
    This is what you're supposed to be hooking into (essential)!
    ~
 /web.config (Other, Included)
    An ASP.NET configuration file (in this instance, to protect the "/vault"
    directory from being accessed by non-authorised sources in the event that
    the script is installed on a server based upon ASP.NET technologies).
    ~
 /_docs/ (Directory)
    Documentation directory (contains various files).
    ~
 /_docs/change_log.txt (Documentation, Included)
    A record of changes made to the script between different
    versions (not required for proper function of script).
    ~
 /_docs/readme.DE.txt (Documentation, Included); DEUTSCH
 /_docs/readme.EN.txt (Documentation, Included); ENGLISH
 /_docs/readme.ES.txt (Documentation, Included); ESPA�OL
 /_docs/readme.FR.txt (Documentation, Included); FRAN�AIS
 /_docs/readme.ID.txt (Documentation, Included); BAHASA INDONESIA
 /_docs/readme.IT.txt (Documentation, Included); ITALIANO
 /_docs/readme.NL.txt (Documentation, Included); NEDERLANDSE
 /_docs/readme.PT.txt (Documentation, Included); PORTUGU�S
    The README files (for example; the file you're currently reading).
    ~
 /_testfiles/ (Directory)
    Test files directory (contains various files).
    All contained files are test files for testing if phpMussel was correctly
    installed on your system, and you do not need to upload this directory
    or any of its files except when doing such testing.
    ~
 /_testfiles/ascii_standard_testfile.txt (Test file, Included)
    Test file for testing phpMussel normalised ASCII signatures.
    ~
 /_testfiles/exe_standard_testfile.exe (Test file, Included)
    Test file for testing phpMussel PE signatures.
    ~
 /_testfiles/general_standard_testfile.txt (Test file, Included)
    Test file for testing phpMussel general signatures.
    ~
 /_testfiles/graphics_standard_testfile.gif (Test file, Included)
    Test file for testing phpMussel graphics signatures.
    ~
 /_testfiles/html_standard_testfile.txt (Test file, Included)
    Test file for testing phpMussel normalised HTML signatures.
    ~
 /_testfiles/md5_testfile.txt (Test file, Included)
    Test file for testing phpMussel MD5 signatures.
    ~
 /_testfiles/metadata_testfile.txt.gz (Test file, Included)
    Test file for testing phpMussel metadata signatures and for testing GZ file
    support on your system.
    ~
 /_testfiles/metadata_testfile.txt.zip (Test file, Included)
    Test file for testing phpMussel metadata signatures and for testing ZIP
    file support on your system.
    ~
 /_testfiles/pe_sectional_testfile.exe (Test file, Included)
    Test file for testing phpMussel PE Sectional signatures.
    ~
 /vault/ (Directory)
    Vault directory (contains various files).
    ~
 /vault/.htaccess (Other, Included)
    A hypertext access file (in this instance, to protect sensitive files
    belonging to the script from being accessed by non-authorised sources).
    ~
 /vault/ascii_clamav_regex.cvd (Signatures, Included)
 /vault/ascii_clamav_regex.map (Signatures, Included)
 /vault/ascii_clamav_standard.cvd (Signatures, Included)
 /vault/ascii_clamav_standard.map (Signatures, Included)
 /vault/ascii_custom_regex.cvd (Signatures, Included)
 /vault/ascii_custom_standard.cvd (Signatures, Included)
 /vault/ascii_mussel_regex.cvd (Signatures, Included)
 /vault/ascii_mussel_standard.cvd (Signatures, Included)
    Files for normalised ASCII signatures.
    Required if normalised ASCII signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/elf_clamav_regex.cvd (Signatures, Included)
 /vault/elf_clamav_regex.map (Signatures, Included)
 /vault/elf_clamav_standard.cvd (Signatures, Included)
 /vault/elf_clamav_standard.map (Signatures, Included)
 /vault/elf_custom_regex.cvd (Signatures, Included)
 /vault/elf_custom_standard.cvd (Signatures, Included)
 /vault/elf_mussel_regex.cvd (Signatures, Included)
 /vault/elf_mussel_standard.cvd (Signatures, Included)
    Files for ELF signatures.
    Required if ELF signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/exe_clamav_regex.cvd (Signatures, Included)
 /vault/exe_clamav_regex.map (Signatures, Included)
 /vault/exe_clamav_standard.cvd (Signatures, Included)
 /vault/exe_clamav_standard.map (Signatures, Included)
 /vault/exe_custom_regex.cvd (Signatures, Included)
 /vault/exe_custom_standard.cvd (Signatures, Included)
 /vault/exe_mussel_regex.cvd (Signatures, Included)
 /vault/exe_mussel_standard.cvd (Signatures, Included)
    Files for Portable Executable file (EXE) signatures.
    Required if EXE signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/filenames_clamav.cvd (Signatures, Included)
 /vault/filenames_custom.cvd (Signatures, Included)
 /vault/filenames_mussel.cvd (Signatures, Included)
    Files for filename signatures.
    Required if filename signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/general_clamav_regex.cvd (Signatures, Included)
 /vault/general_clamav_regex.map (Signatures, Included)
 /vault/general_clamav_standard.cvd (Signatures, Included)
 /vault/general_clamav_standard.map (Signatures, Included)
 /vault/general_custom_regex.cvd (Signatures, Included)
 /vault/general_custom_standard.cvd (Signatures, Included)
 /vault/general_mussel_regex.cvd (Signatures, Included)
 /vault/general_mussel_standard.cvd (Signatures, Included)
    Files for general signatures.
    Required if general signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/graphics_clamav_regex.cvd (Signatures, Included)
 /vault/graphics_clamav_regex.map (Signatures, Included)
 /vault/graphics_clamav_standard.cvd (Signatures, Included)
 /vault/graphics_clamav_standard.map (Signatures, Included)
 /vault/graphics_custom_regex.cvd (Signatures, Included)
 /vault/graphics_custom_standard.cvd (Signatures, Included)
 /vault/graphics_mussel_regex.cvd (Signatures, Included)
 /vault/graphics_mussel_standard.cvd (Signatures, Included)
    Files for graphics signatures.
    Required if graphics signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/greylist.csv (Signatures, Included/Created)
    CSV of greylisted signatures indicating to phpMussel which signatures it
    should be ignoring (file automatically recreated if deleted).
    ~
 /vault/hex_general_commands.csv (Signatures, Included)
    Hex-encoded CSV of general command detections optionally used by phpMussel.
    Required if general command detection option in phpmussel.ini is enabled.
    Can remove if option is disabled (but file will be recreated on update).
    ~
 /vault/html_clamav_regex.cvd (Signatures, Included)
 /vault/html_clamav_regex.map (Signatures, Included)
 /vault/html_clamav_standard.cvd (Signatures, Included)
 /vault/html_clamav_standard.map (Signatures, Included)
 /vault/html_custom_regex.cvd (Signatures, Included)
 /vault/html_custom_standard.cvd (Signatures, Included)
 /vault/html_mussel_regex.cvd (Signatures, Included)
 /vault/html_mussel_standard.cvd (Signatures, Included)
    Files for normalised HTML signatures.
    Required if normalised HTML signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/lang.inc (Script, Included)
    phpMussel Language Data; Required for multilingual capabilities.
    ~
 /vault/macho_clamav_regex.cvd (Signatures, Included)
 /vault/macho_clamav_regex.map (Signatures, Included)
 /vault/macho_clamav_standard.cvd (Signatures, Included)
 /vault/macho_clamav_standard.map (Signatures, Included)
 /vault/macho_custom_regex.cvd (Signatures, Included)
 /vault/macho_custom_standard.cvd (Signatures, Included)
 /vault/macho_mussel_regex.cvd (Signatures, Included)
 /vault/macho_mussel_standard.cvd (Signatures, Included)
    Files for Mach-O signatures.
    Required if Mach-O signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/mail_clamav_regex.cvd (Signatures, Included)
 /vault/mail_clamav_regex.map (Signatures, Included)
 /vault/mail_clamav_standard.cvd (Signatures, Included)
 /vault/mail_clamav_standard.map (Signatures, Included)
 /vault/mail_custom_regex.cvd (Signatures, Included)
 /vault/mail_custom_standard.cvd (Signatures, Included)
 /vault/mail_mussel_regex.cvd (Signatures, Included)
 /vault/mail_mussel_standard.cvd (Signatures, Included)
    Files for signatures used by the phpMussel_mail() function.
    Required if the phpMussel_mail() function is used in any way.
    Can remove if it is not used (but files will be recreated on update).
    ~
 /vault/md5_clamav.cvd (Signatures, Included)
 /vault/md5_custom.cvd (Signatures, Included)
 /vault/md5_mussel.cvd (Signatures, Included)
    Files for MD5 based signatures.
    Required if MD5 based signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/metadata_clamav.cvd (Signatures, Included)
 /vault/metadata_custom.cvd (Signatures, Included)
 /vault/metadata_mussel.cvd (Signatures, Included)
    Files for archive metadata signatures.
    Required if archive metadata signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/pe_clamav.cvd (Signatures, Included)
 /vault/pe_custom.cvd (Signatures, Included)
 /vault/pe_mussel.cvd (Signatures, Included)
    Files for PE Sectional signatures.
    Required if PE Sectional signatures option in phpmussel.ini is enabled.
    Can remove if option is disabled (but files will be recreated on update).
    ~
 /vault/phpmussel.inc (Script, Included)
    phpMussel Core Script; The main body and guts of phpMussel (essential)!
    ~
 /vault/phpmussel.ini (Other, Included)
    phpMussel Configuration file; Contains all the configuration options of
    phpMussel, telling it what to do and how to operate correctly (essential)!
    ~
 /vault/scan_log.txt *(Logfile, Created)
    A record of everything scanned by phpMussel.
    ~
 /vault/scan_kills.txt *(Logfile, Created)
    A record of every file upload blocked/killed by phpMussel.
    ~
 /vault/template.html (Other, Included)
    phpMussel Template file; Template for HTML output produced by phpMussel for
    its blocked file upload message (the message seen by the uploader).
    ~
 /vault/update.dat (Other, Included)
    File containing version information for both the phpMussel script and the
    phpMussel signatures. If you ever want to automatically update phpMussel or
    want to update phpMusel via your browser, this file is essential.
    ~
 /vault/update.inc (Script, Included)
    phpMussel Update Script; Required for automatic updates and for updating
    phpMussel via your browser, but not required otherwise.
    ~
 /vault/whitelist_clamav.cvd (Signatures, Included)
 /vault/whitelist_custom.cvd (Signatures, Included)
 /vault/whitelist_mussel.cvd (Signatures, Included)
    File specific whitelist.
    Required if whitelisting option in phpmussel.ini is enabled and if you wish
    to have specific files whitelisted. Can remove if option is disabled or if
    you don't require whitelisting (but files will be recreated on update).
    ~

 * Filename may differ based on configuration stipulations (in phpmussel.ini).

 = REGARDING SIGNATURE FILES =
    CVD is an acronym for "ClamAV Virus Definitions", in reference both to
    how ClamAV refers to its own signatures and to the use of those signatures
    for phpMussel; Files ending with "CVD" contain signatures.
    ~
    Files ending with "MAP", quite literally, map which signatures phpMussel
    should and shouldn't use for individual scans; Not all signatures are
    necessarily required for every single scan, so, phpMussel uses maps of the
    signature files to speed up the scanning process (a process which would
    otherwise be extremely slow and tedious).
    ~
    Signature files marked with "_regex" contain signatures which utilise
    regular expression pattern checking (regex).
    ~
    Signature files marked with "_standard" contain signatures which
    specifically do not utilise any form of pattern checking.
    ~
    Signature files marked with neither "_regex" nor "_standard" will be as one
    or the other, but not both (refer to the Signature Format section of this
    README file for documentation and specific details).
    ~
    Signature files marked with "_clamav" contain signatures that are sourced
    entirely from the ClamAV database (GNU/GPL).
    ~
    Signature files marked with "_custom", by default, do not contain any
    signatures at all; These such files exist to give you somewhere to place
    your own custom signatures, if you come up with any of your own.
    ~
    Signature files marked with "_mussel" contain signatures that specifically
    are not sourced from ClamAV, signatures which, generally, I've either come
    up with myself and/or based on information gathered from various sources.
    ~

                                     ~ ~ ~                                     


 6. CONFIGURA��O OP��ES

 The following is a list of variables found in the "phpmussel.ini"
 configuration file of phpMussel, along with a description of their purpose and
 function.

 "general" (Category)
 - General configuration for phpMussel.
    "script_password"
    - As a convenience, phpMussel will allow certain functions (including the
      ability to update phpMussel on-the-fly) to be manually triggered via
      POST, GET and QUERY. However, as a security precaution, to do this,
      phpMussel will expect a password to be included with the command, as to
      ensure that it is you, and not someone else, attempting to manually
      trigger these functions. Set script_password to whatever password you
      would like to use. If no password is set, manual triggering will be
      disabled by default. Use something you will remember but which is hard
      for others to guess.
      * Has no influence in CLI mode.
    "logs_password"
    - The same as script_password, but for viewing the contents of scan_log
      and scan_kills. Having separate passwords can be useful if you want to
      give someone else access to one set of functions but not the other.
      * Has no influence in CLI mode.
    "cleanup"
    - Unset script variables and cache after execution. If you aren't using
      the script beyond the initial scanning of uploads, should set to yes, to
      minimize memory usage. If you are using the script for purposes beyond
      the initial scanning of uploads, should set to no, to avoid unnecessarily
      reloading duplicate data into memory. In general practise, it should
      probably be set to yes, but, if you do this, you won't be able to use the
      script for anything other than scanning file uploads.
      * Has no influence in CLI mode.
    "scan_log"
    - Filename of file to log all scanning results to. Specify a filename, or
      leave blank to disable.
    "scan_kills"
    - Filename of file to log all records of blocked or killed uploads to.
      Specify a filename, or leave blank to disable.
    "ipaddr"
    - Where to find IP address of connecting request? (Useful for services
      such as Cloudflare and the likes) Default = REMOTE_ADDR
      WARNING: Don't change this unless you know what you're doing!
    "forbid_on_block"
    - Should phpMussel send 403 headers with the file upload blocked message,
      or stick with the usual 200 OK? 0 = No (200) [Default], 1 Yes (403).
    "delete_on_sight"
    - Switching on this option will instruct the script to attempt to
      immediately delete any file it finds during its scans that matches any
      detection criteria, whether via signatures or otherwise. Files determined
      to be "clean" will not be touched. In the case of archives, the entire
      archive will be deleted (regardless of if the offending file is only one
      of several files contained within the archive). For the case of file
      upload scanning, usually, it isn't necessary to turn this option on,
      because usually, php will automatically purge the contents of its cache
      when execution has finished, meaning that it'll usually delete any files
      uploaded through it to the server unless they've moved, copied or deleted
      already. The option is added here as an extra measure of security for the
      extra paranoid and for those whose copies of php may not always behave in
      the manner intended.
      0 - After scanning, leave the file alone [Default],
      1 - After scanning, if not clean, delete immediately.
    "lang"
    - Specify the default language for phpMussel.
 "signatures" (Category)
 - Configuration for signatures.
   %%%_clamav = ClamAV signatures (both mains and daily).
   %%%_custom = Your custom signatures (if you've written any).
   %%%_mussel = phpMussel signatures included in your current signatures set
                which aren't from ClamAV.
   - Check against MD5 signatures when scanning?
     0 = No, 1 = Yes [Default].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Check against general signatures when scanning?
     0 = No, 1 = Yes [Default].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Check against normalised ASCII signatures when scanning?
     0 = No, 1 = Yes [Default].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - Check against normalised HTML signatures when scanning?
     0 = No, 1 = Yes [Default].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - Check PE (portable executable) files (EXE, DLL, etc) against PE Sectional
     signatures when scanning?
     0 = No, 1 = Yes [Default].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Check PE (portable executable) files (EXE, DLL, etc) against PE signatures
     when scanning?
     0 = No, 1 = Yes [Default].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Check ELF files against ELF signatures when scanning?
     0 = No, 1 = Yes [Default].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Check Mach-O files (OSX, etc) against Mach-O signatures when scanning?
     0 = No, 1 = Yes [Default].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Check graphics files against graphics based signatures when scanning?
     0 = No, 1 = Yes [Default].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Check archive contents against archive metadata signatures when scanning?
     0 = No, 1 = Yes [Default].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Check filenames against filename based signatures when scanning?
     0 = No, 1 = Yes [Default].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Allow scanning with phpMussel_mail()?
     0 = No, 1 = Yes [Default].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Signature matching length limiting options. Only change these if you
     know what you're doing. SD = Standard signatures. RX = PCRE (Perl
     Compatible Regular Expressions, or "Regex") signatures. FN = Filename
     signatures. If you notice php crashing when phpMussel attempts to scan,
     try lowering the "max" values below. If possible and convenient, let me
     know when this happens and the results of whatever you try.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Should phpMussel report when signatures files are missing or corrupted?
     If fail_silently is disabled, missing and corrupted files will be reported
     on scanning, and if fail_silently is enabled, missing and corrupted files
     will be ignored, with scanning reported for those files that there are no
     problems. This should generally be left alone unless you're experiencing
     crashes or similar problems.
     0 = Disabled [Default], 1 = Enabled.
     "fail_silently"
 "files" (Category)
 - General configuration for handling of files.
   "max_uploads"
   - Maximum allowable number of files to scan during files upload scan before
     aborting the scan and informing the user they are uploading too much at
     once! Provides protection against a theoretical attack whereby an attacker
     attempts to DDoS your system or CMS by overloading phpMussel to slow down
     the php process to a grinding halt. Recommended: 10. You may wish to raise
     or lower this number depending on the speed of your hardware. Note that
     this number does not account for or include the contents of archives.
   "filesize_limit"
   - Filesize limit in KB. 65536 = 64MB [Default], 0 = No limit (always
     greylisted), any (positive) numeric value accepted. This can be useful
     when your php configuration limits the amount of memory a process can hold
     or if your php configuration limits filesize of uploads.
   "filesize_response"
   - What to do with files that exceed the filesize limit (if one exists).
     0 - Whitelist, 1 - Blacklist [Default].
   "filetype_whitelist" and "filetype_blacklist"
   - If your system only allows specific types of files to be uploaded, or if
     your system explicitly denies certain types of files, specifying those
     filetypes in whitelists and blacklists can increase the speed at which
     scanning is performed by allowing the script to skip over certain
     filetypes. Format is CSV (comma separated values). If you want to scan
     everything, rather than whitelist or blacklist, leave the variable(/s)
     blank (doing so will disable whitelist/blacklist).
   "check_archives"
   - Attempt to check the contents of archives?
     0 - No (do not check), 1 - Yes (check) [Default].
     * Currently, only checking of BZ, GZ, LZF and ZIP files is supported
       (checking of RAR, CAB, 7z and etcetera not currently supported).
     * This is not foolproof! While I highly recommend keeping this turned on,
       I can't guarantee it'll always find everything.
     * Also be aware that archive checking currently is not recursive for ZIPs.
   "filesize_archives"
   - Carry over filesize blacklisting/whitelisting to the contents of archives?
     0 - No (just greylist everything), 1 - Yes [Default].
   "filetype_archives"
   - Carry over filetype blacklisting/whitelisting to the contents of archives?
     0 - No (just greylist everything) [Default], 1 - Yes.
   "max_recursion"
   - Maximum recursion depth limit for archives. Default = 10.
 "attack_specific" (Category)
 - Configuration for specific attack detections (not based on CVDs).
   * Chameleon attack detection: 0 = Off, 1 = On.
   "chameleon_from_php"
   - Search for php header in files that are neither php files nor recognised
     archives.
   "chameleon_from_exe"
   - Search for executable headers in files that are neither executables nor
     recognised archives and for executables whose headers are incorrect.
   "chameleon_to_archive"
   - Search for archives whose headers are incorrect (Supported: BZ, GZ, RAR,
     ZIP, RAR, GZ).
   "chameleon_to_doc"
   - Search for office documents whose headers are incorrect (Supported: DOC,
     DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Search for images whose headers are incorrect (Supported: BMP, DIB, PNG,
     GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Search for PDF files whose headers are incorrect.
   "archive_file_extensions" and "archive_file_extensions_wc"
   - Recognised archive file extensions (format is CSV; should only add or
     remove when problems occur; unnecessarily removing may cause
     false-positives to appear for archive files, whereas unnecessarily adding
     will essentially whitelist what you are adding from attack specific
     detection; modify with caution; also note that this has no effect on what
     archives can and can't be analysed at content-level). The list, as is at
     default, lists those formats used most commonly across the majority of
     systems and CMS, but intentionally isn't necessarily comprehensive.
   "general_commands"
   - Search content of files for general commands such as eval(), exec() and
     include()? 0 - No (do not check) [Default], 1 - Yes (check).
     Turn this option off if you intend to upload any of the following to your
     system or CMS via your browser: php, JavaScript, HTML, python, perl files
     and etcetera. Turn this option on if you do not have any additional
     protections on your system and do not intend to upload such files. If you
     use additional security in conjunction with phpMussel such as ZB Block,
     there is no need to turn this option on, because most of what phpMussel
     will look for (in the context of this option) are duplications of
     protections that are already provided.
   "block_control_characters"
   - Block any files containing any control characters (other than newlines)?
     ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) If you are -only- uploading plain-text,
     then you can turn this option on to provide some additional protection to
     your system. However, if you upload anything other than plain-text,
     turning this on may result in false positives.
     0 - Don't block [Default], 1 - Block.
   "corrupted_exe"
   - Corrupted files and parse errors. 0 = Ignore, 1 = Block [Default].
     Detect and block potentially corrupted PE (portable executable) files?
     Often (but not always), when certain aspects of a PE file are corrupted or
     can't be parsed correctly, it can be indicative of a viral infection. The
     processes used by most anti-virus programs to detect viruses in PE files
     require parsing those files in certain ways, which, if the programmer of a
     virus is aware of, will specifically try to prevent, in order to allow
     their virus to remain undetected.
   "decode_threshold"
   - Optional limitation or threshold to the length of raw data to which within
     decode commands should be detected (in case there are any noticeable
     performance issues whilst scanning). Value is an integer representing
     filesize in KB. Default = 512 (512KB). Zero or null value disables the
     threshold (removing any such limitation based on filesize).
   "scannable_threshold"
   - Optional limitation or threshold to the length of raw data to which
     phpMussel is permitted to read and scan (in case there are any noticeable
     performance issues whilst scanning). Value is an integer representing
     filesize in KB. Default = 32768 (32MB). Generally, this value shouldn't be
     less than the average filesize of file uploads that you want and expect to
     receive to your server or website, shouldn't be more than the
     filesize_limit directive, and shouldn't be more than roughly one fifth of
     the total allowable memory allocation granted to php via the php.ini
     configuration file. This directive exists to try to prevent phpMussel from
     using up too much memory (which would prevent it from being able to
     successfully scan files above a certain filesize).
 "compatibility" (Category)
 - Compatibility directives for phpMussel.
    "ignore_upload_errors"
    - This directive should generally be switched OFF unless it is required for
      correct functionality of phpMussel on your specific system. Normally,
      when switched OFF, when phpMussel detects the presence of elements in the
      $_FILES array(), it will attempt to initiate a scan of the files that
      those elements represent, and, if those elements are blank or empty,
      phpMussel will return an error message. This is proper behaviour for
      phpMussel. However, for some CMS, empty elements in $_FILES can occur as
      a result of the natural behaviour of those CMS, or errors may be reported
      when there aren't any, in which case, the normal behaviour for phpMussel
      will be interfering with the normal behaviour of those CMS. If such a
      situation occurs for you, turning this option ON will instruct phpMussel
      to not attempt to initiate scans for such empty elements, ignore them
      when found and to not return any related error messages, thus allowing
      continuation of the page request. 0 - OFF, 1 - ON.


                                     ~ ~ ~                                     


 7. ASSINATURA FORMATO

 = MD5 SIGNATURES =
   All MD5 signatures follow the format:
    HASH:FILESIZE:NAME
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size
   of that file and NAME is the name to cite for that signature.

 = PE SECTIONAL MD5 SIGNATURES =
   All PE Sectional MD5 signatures follow the format:
    FILESIZE:HASH:NAME
   Where HASH is the MD5 hash of a section of the PE file, FILESIZE is the
   total size of that file and NAME is the name to cite for that signature.

 = WHITELIST SIGNATURES =
   All Whitelist signatures follow the format:
    HASH:FILESIZE:TYPE
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size
   of that file and TYPE is the type of signatures the whitelisted file is to be
   immune against.

 = FILENAME SIGNATURES =
   All filename signatures follow the format:
    NAME:FNRX
   Where NAME is the name to cite for that signature and FNRX is the regex
   pattern to match filenames (unencoded) against.

 = ARCHIVE METADATA SIGNATURES =
   All archive metadata signatures follow the format:
    NAME:FILESIZE:CRC32
   Where NAME is the name to cite for that signature, FILESIZE is the total
   size (uncompressed) of a file contained within the archive and CRC32 is
   the crc32 checksum of that contained file.

 = EVERYTHING ELSE =
   All other signatures follow the format:
    NAME:HEX:FROM:TO
   Where NAME is the name to cite for that signature and HEX is a
   hexadecimal-encoded segment of the file intended to be matched by
   the given signature. FROM and TO are optional parameters, indicting from
   which and to which positions in the source data to check against (not
   supported by the mail function).

 = REGEX =
   Any form of regex understood and correctly processed by php should also be
   correctly understood and processed by phpMussel and its signatures.
   However, I'd suggest taking extreme caution when writing new regex based
   signatures, because, if you're not entirely sure what you're doing, there
   can be highly irregular and/or unexpected results. Take a look at the
   phpMussel source-code if you're not entirely sure about the context in
   which regex statements are parsed. Also, remember that all patterns (with
   exception to filename, archive metadata and MD5 patterns) must be
   hexadecimally encoded (foregoing pattern syntax, of course)!

 = WHERE TO PUT CUSTOM SIGNATURES? =
   Only put custom signatures in those files intended for custom signatures.
   Those files should contain "_custom" in their filenames.
   You should also avoid editing the default signature files, unless you know
   exactly what you're doing, because, aside from being good practise in
   general and aside from helping you distinguish between your own signatures
   and the default signatures included with phpMussel, it is good to stick to
   editing only the files intended for editing, because tampering with the
   default signature files can cause them to stop working correctly, due to the
   "maps" files: The maps files tell phpMussel where in the signature files to
   look for signatures required by phpMussel as per when required, and these
   maps can become out-of-sync with their associated signature files if those
   signature files are tampered with. You can put pretty much whatever you want
   into your custom signatures, so long as you follow the correct syntax.
   However, be careful to test new signatures for false-positives beforehand
   if you intend to share them or use them in a live environment.

 = SIGNATURE BREAKDOWN =
   The following is a breakdown of the types of signatures used by phpMussel:
   - "MD5 Signatures" (md5_*). Checked against the MD5 hash of the contents and
      the filesize of every non-whitelisted file targeted for scanning.
   - "General Signatures" (general_*). Checked against the contents of every
      non-whitelisted file targeted for scanning.
   - "Normalised ASCII Signatures" (ascii_*). Checked against the contents of
      every non-whitelisted file targeted for scanning.
   - "Normalised HTML Signatures" (html_*). Checked against the contents of
      every non-whitelisted HTML file targeted for scanning.
   - "General Commands" (hex_general_commands.csv). Checked against the
      contents of every non-whitelisted file targeted for scanning.
   - "Portable Executable Sectional Signatures" (pe_*). Checked against the
      contents of every non-whitelisted targeted for scanning and matched to
      the PE format.
   - "Portable Executable Signatures" (exe_*). Checked against the contents of
      every non-whitelisted targeted for scanning and matched to the PE format.
   - "ELF Signatures" (elf_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to the ELF format.
   - "Graphics Signatures" (graphics_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to a known
      graphical file format.
   - "Mach-O Signatures" (macho_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to the Mach-O
      format.
   - "Archive Metadata Signatures" (metadata_*). Checked against the CRC32 hash
      and filesize of the initial file contained inside of any non-whitelisted
      archive targeted for scanning.
   - "Email Signatures" (mail_*). Checked against the $body variable parsed to
      the phpMussel_mail() function, which is intended to be the body of email
      messages or similar entities (potentially forum posts and etcetera).
   - "Whitelist Signatures" (whitelist_*). Checked against the MD5 hash of the
      contents and the filesize of every file targeted for scanning. Matched
      files will be immune to being matched by the type of signature mentioned
      in their whitelist entry.
     (Note that any of these signatures may be easily disabled via
      phpmussel.ini).


                                     ~ ~ ~                                     


 8. CONHECIDOS COMPATIBILIDADE PROBLEMAS

 PHP e PCRE
 - phpMussel requer PHP e PCRE para executar e funcionar corretamente. Sem php,
   ou sem a PCRE extens�o do PHP, phpMussel n�o vai executar� ou funcionar
   corretamente. Deve certificar-se de que seu sistema tenha PHP e PCRE
   instalado e dispon�vel antes de baixar e instalar phpMussel.

 ANTI-V�RUS SOFTWARE COMPATIBILIDADE

 Em geral, phpMussel deve ser bastante compat�vel com a maioria dos outros
 v�rus detec��o softwares. Embora, conflitos foram relatadas por um n�mero de
 utilizadores no passado. Esta informa��o abaixo � de VirusTotal.com, e
 descreve um n�mero de falso-positivos relatados por v�rios anti-v�rus
 programas contra phpMussel. Embora esta informa��o n�o � uma garantia absoluta
 de haver ou n�o voc� vai encontrar problemas de compatibilidade entre
 phpMussel e seu anti-v�rus software, se o seu anti-v�rus software � conhecido
 como sinaliza��o contra phpMussel, voc� deve considerar desativ�-lo antes de
 trabalhar com phpMussel ou deve considerar alternativas op��es para o seu
 anti-v�rus software ou phpMussel.

 Esta informa��o foi atualizada dia 13 Setembro 2014 e � corrente para todas
 phpMussel lan�amentos das duas mais recentes menores vers�es (v0.3-v0.4d) no
 momento de escrever este.

 Ad-Aware                Sem conhecidos problemas
 Agnitum                 Sem conhecidos problemas
 AhnLab-V3               Sem conhecidos problemas
 AntiVir                 Sem conhecidos problemas
 Antiy-AVL               Sem conhecidos problemas
 Avast                !  Reportar "JS:ScriptSH-inf [Trj]"
                         - Todos, exceto v0.3d, v0.4d
 AVG                     Sem conhecidos problemas
 Baidu-International     Sem conhecidos problemas
 BitDefender             Sem conhecidos problemas
 Bkav                 !  Reportar "VEX408f.Webshell"
                         - v0.3 a v0.3c
 ByteHero                Sem conhecidos problemas
 CAT-QuickHeal           Sem conhecidos problemas
 ClamAV                  Sem conhecidos problemas
 CMC                     Sem conhecidos problemas
 Commtouch            !  Reportar "W32/GenBl.857A3D28!Olympus"
                         - v0.3e s�
 Comodo                  Sem conhecidos problemas
 DrWeb                   Sem conhecidos problemas
 Emsisoft                Sem conhecidos problemas
 ESET-NOD32              Sem conhecidos problemas
 F-Prot                  Sem conhecidos problemas
 F-Secure                Sem conhecidos problemas
 Fortinet                Sem conhecidos problemas
 GData                !  Reportar "Archive.Trojan.Agent.E7C7J7"
                         - v0.3e s�
 Ikarus               !  Reportar "Trojan.JS.Agent"
                         - v0.3g a v0.4c
 Jiangmin                Sem conhecidos problemas
 K7AntiVirus             Sem conhecidos problemas
 K7GW                    Sem conhecidos problemas
 Kaspersky               Sem conhecidos problemas
 Kingsoft                Sem conhecidos problemas
 Malwarebytes            Sem conhecidos problemas
 McAfee                  Sem conhecidos problemas
 McAfee-GW-Edition       Sem conhecidos problemas
 Microsoft               Sem conhecidos problemas
 MicroWorld-eScan        Sem conhecidos problemas
 NANO-Antivirus          Sem conhecidos problemas
 Norman               !  Reportar "Kryptik.BQS"
                         - Todos, exceto v0.3d, v0.3e, v0.4d
 nProtect                Sem conhecidos problemas
 Panda                   Sem conhecidos problemas
 Qihoo-360               Sem conhecidos problemas
 Rising                  Sem conhecidos problemas
 Sophos                  Sem conhecidos problemas
 SUPERAntiSpyware        Sem conhecidos problemas
 Symantec                Sem conhecidos problemas
 TheHacker               Sem conhecidos problemas
 TotalDefense            Sem conhecidos problemas
 TrendMicro              Sem conhecidos problemas
 TrendMicro-HouseCall !  Reportar "Suspici.450F5936"
                         - v0.3d a v0.4c
 VBA32                   Sem conhecidos problemas
 VIPRE                   Sem conhecidos problemas
 ViRobot                 Sem conhecidos problemas


                                     ~ ~ ~                                     


�ltima Atualiza��o: 13 Setembro 2014 (2014.09.13).
EOF
      _____  _     _  _____  _______ _     _ _______ _______ _______
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____

                            { ~ ~ ~ ESPA�OL ~ ~ ~ }
 CONTENIDOS
 1. PRE�MBULO
 2A. C�MO INSTALAR (PARA NAVEGADORES)
 2B. C�MO INSTALAR (PARA CLI)
 3A. C�MO USO (PARA NAVEGADORES)
 3B. C�MO USO (PARA CLI)
 4A. NAVEGADOR COMANDOS
 4B. CLI (COMANDOS L�NEA INTERFAZ)
 5. ARCHIVOS INCLUIDOS EN ESTE PAQUETE
 6. CONFIGURACI�N OPCIONES
 7. FIRMA FORMATOS
 8. CONOCIDOS PROBLEMAS DE COMPATIBILIDAD

                                     ~ ~ ~


 1. PRE�MBULO

 Gracias por usar phpMussel, un PHP script dise�ado para detectar troyanos,
 virus, malware y otras amenazas en los archivos cargados en el sistema donde
 el script est� adjunto, basado en las firmas de ClamAV y otros.

 PHPMUSSEL COPYRIGHT 2013 and beyond GNU/GPL V.2 by Caleb M (Maikuolan).

 Este script es gratis software; puede redistribuirlo y/o modificarlo seg�n los
 t�rminos de la GNU General P�blica Licencia como publicada por la Free
 Software Foundation; versi�n 2 de la licencia, o cualquier posterior versi�n.
 Este script se distribuye con la esperanza de que ser� �til, pero SIN NINGUNA
 GARANT�A; tambi�n, sin ninguna impl�cita garant�a de COMERCIALIZACI�N o
 IDONEIDAD PARA UN PARTICULAR PROP�SITO. Vea la GNU General P�blica Licencia
 para m�s detalles. <http://www.gnu.org/licenses/>
 <http://opensource.org/licenses/>

 Un especial agradecimiento a ClamAV para la inspiraci�n del proyecto y para
 las firmas que este script utiliza, sin la cual, el gui�n probablemente no
 existir�a, o en el mejor de, tendr�a un muy limitado valor
 <http://www.clamav.net/>.

 Un especial agradecimiento a Sourceforge para alojar los archivos de proyecto,
 situado en <http://sourceforge.net/projects/phpmussel/>, a Spambot Security
 para la phpMussel discusi�n foros, situado en
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, y a las adicionales
 fuentes de un n�mero de las firmas utilizadas por phpMussel: SecuriteInfo.com
 <http://www.securiteinfo.com/>, PhishTank <http://www.phishtank.com/>,
 NLNetLabs <http://nlnetlabs.nl/> y otros, y agradecimiento especial a todos
 aquellos que apoyan el proyecto, a cualquier otra persona que yo haya olvidado
 de lo contrario mencionar, y a usted, por el uso de la script.

 Este documento y asociado paquete pueden descargar de gratis desde
 Sourceforge <http://sourceforge.net/projects/phpmussel/>.

                                     ~ ~ ~


 2A. C�MO INSTALAR (PARA NAVEGADORES)

 Espero para agilizar este proceso al hacer un instalador en alg�n momento en
 un futuro no muy lejano, pero hasta entonces, siga estas instrucciones para ha
 phpMussel functione en *mayor�a de sistemas y CMS:

 1) Con tu leyendo esto, estoy asumiendo que usted ha descargado una archivada
    copia de la script, descomprimido y tenerlo en alg�n lugar en su computer.
    Desde aqu�, usted querr� averiguar d�nde en el host o CMS que desea para
    colocar el contenido. Un directorio como /public_html/phpmussel/ o similar
    (aunque, no importa que usted elija, a condici�n de que se algo que est�s
    satisfecho con) ser� suficiente. Antes usted enviar archivos a su host,
    seguir leyendo..

 2) Abrir "phpmussel.php", busque la l�nea que comienza con "$vault=", y
    reemplazar la cadena entre las siguientes comillas en esa l�nea con la
    exacta verdadera ubicaci�n del "vault" directorio de phpMussel. Usted ver�
    tal un directorio en el archivado que ha descargado (asumiendo que no desea
    revolver todo el gui�n, mantener la misma estructura de archivos y
    directorios como lo fue el original). Este "vault" directorio normalmente
    es un directorio nivel m�s all� del directorio que existir� en el
    "phpmussel.php" archivo. Guardar el archivo, cerrar.

 3) (Opcional; Muy recomendable para avanzados usuarios, pero no se recomienda
    para los principiantes o para los inexpertos): Abrir "phpmussel.ini"
    (situado en el interior del "vault") - Este archivo contiene todas las
    disponibles operativas opciones para phpMussel. Por encima de cada opci�n
    debe ser un breve comentario que describe lo que hace y para lo qu� sirve.
    Ajuste estas opciones seg�n sus necesidades, seg�n lo que sea apropiado
    para su particular configuraci�n. Guardar archivo, cerrar.

 4) Cargar contenido (phpMussel y sus archivos) al directorio que hab�as
    decidido sobre m�s temprano (no es necesario el readme.XX.txt archivo o el
    change_log.txt archivo, pero, en su mayor�a, usted debe cargar todos).

 5) CMHOD al "vault" directorio a "777". La principal directorio de
    almacenamiento de los contenidos (el uno decidi� desde antes), en general,
    puede dejar solos, pero CHMOD estado debe comprobar si ha tenido problemas
    de permisos en el pasado en su sistema (por defecto, debe ser algo como
    "755").

 6) Luego, tendr�s que phpMussel "gancho" para el sistema o CMS. Hay varias
    maneras en que usted puede "gancho" scripts como phpMussel a su sistema o
    CMS, pero lo m�s f�cil es simplemente incluir el script al principio de un
    n�cleo archivo de su sistema o CMS (uno que va por lo general siempre se va
    cargado cuando alguien accede cualquier p�gina a trav�s de su website)
    utilizando un require o include comando. Por lo general, esto va ser algo
    almacenado en un directorio como "/includes", "/assets" o "/functions", y
    ser� menudo llamado algo as� como "init.php", "common_functions.php",
    "functions.php" o similar. Vas a tener que averiguar qu� archivo se por su
    situaci�n. Para ello, inserte la siguiente l�nea de c�digo al principio de
    ese n�cleo archivo, con sustituci�n de la string contenida dentro las
    comillas con la exacta direcci�n del "phpmussel.php" archivo (local
    direcci�n, no la HTTP direcci�n; que ser� similar a la "vault" direcci�n
    mencion� anteriormente).

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Guardar archivo, cerrarla, recargar.

 7) Con eso, ya est�! Pero, probablemente deber�as preubalo para asegurarse de
    que est� funcionando correctamente. Para probar archivos carga
    protecciones, probar cargar los prueba archivos incluidos en el paquete
    dentro "_testfiles" a su website a trav�s de sus habituales navegador
    basado cargar m�todos. Si todo funciona correctamente, un mensaje debe
    aparecer de phpMussel confirmando que la carga ha sido bloqueada con �xito.
    Si nada aparece, algo no est� funcionando correctamente. Si est� utilizando
    cualquiera de las avanzadas funciones o si est� utilizandolos otros tipos
    de escaneo posible, Sugiero probarlo con aquellos a asegurarse de que
    funciona como se espera, tambi�n.

                                     ~ ~ ~


 2B. C�MO INSTALAR (PARA CLI)

 Espero para agilizar este proceso al hacer un instalador en alg�n momento en
 un futuro no muy lejano, pero hasta entonces, siga estas instrucciones para ha
 phpMussel listo para trabajar con CLI (ser conscientes de que en este momento,
 CLI apoyo s�lo se aplica a los Windows basados sistemas; Linux y otros
 sistemas vendr�n pronto a una posterior versi�n de phpMussel):

 1) Con tu leyendo esto, estoy asumiendo que usted ha descargado una archivada
    copia de la script, descomprimido y tenerlo en alg�n lugar en su computer.
    Cuando se ha determinado que usted es feliz con el lugar elegido para
    phpMussel, contin�e.

 2) phpMussel requiere php para ser instalado en la host m�quina para ejecutar.
    Si usted no has php instalado en su m�quina, por favor, instalar php en su
    m�quina, siguiendo las instrucciones suministradas por el php instalador.

 3) Abrir "phpmussel.php", busque la l�nea que comienza con "$vault=", y
    reemplazar la cadena entre las siguientes comillas en esa l�nea con la
    exacta verdadera ubicaci�n del "vault" directorio de phpMussel. Usted ver�
    tal un directorio en el archivado que ha descargado (asumiendo que no desea
    revolver todo el gui�n, mantener la misma estructura de archivos y
    directorios como lo fue el original). Este "vault" directorio normalmente
    es un directorio nivel m�s all� del directorio que existir� en el
    "phpmussel.php" archivo. Guardar el archivo, cerrar.

 4) (Opcional; Muy recomendable para avanzados usuarios, pero no se recomienda
    para los principiantes o para los inexpertos): Abrir "phpmussel.ini"
    (situado en el interior del "vault") - Este archivo contiene todas las
    disponibles operativas opciones para phpMussel. Por encima de cada opci�n
    debe ser un breve comentario que describe lo que hace y para lo qu� sirve.
    Ajuste estas opciones seg�n sus necesidades, seg�n lo que sea apropiado
    para su particular configuraci�n. Guardar archivo, cerrar.

 5) (Opcional) Usted puede hacer uso de phpMussel en CLI modo m�s f�cil para ti
    mismo mediante la creaci�n de un batch archivo para autom�ticamente cargar
    php y phpMussel. Para ello, abra un texto editor como Notepad o Notepad++,
    escriba la completa ruta al "php.exe" archivo dentro lo directorio de la
    php instalaci�n, seguido de un espacio, seguido de la completa ruta al
    "phpmussel.php" archivo dentro lo directorio de su phpMussel instalaci�n,
    guardar el archivo con la ".bat" extensi�n en alguna parte que usted lo
    encontrar� f�cilmente, y haga doble clic en ese archivo para ejecutar
    phpMussel en el futuro.

 6) Con eso, ya est�! Pero, probablemente deber�as preubalo para asegurarse de
    que est� funcionando correctamente. Para probar phpMussel, ejecute
    phpMussel e probar escanear el directorio "_testfiles" suministrada con el
    paquete.

                                     ~ ~ ~


 3A. C�MO USO (PARA NAVEGADORES)

 phpMussel es un script dise�ado para funcionar adecuadamente, inmediatamente,
 con m�nimo nivel de requisitos en su nombre: Cuando se ha instalado,
 b�sicamente, que simplemente deber�a funcionar.

 Escaneo de archivos cargas es automatizado y activado como est�ndar, as�, nada
 se requerida en su nombre por esta particular funci�n.

 Pero, tambi�n es capaz instruir� phpMussel para escanear archivos, directorios
 o compactos archivos usted especifique impl�citamente. Para ello,
 primeramente, usted tendr� asegurarse de que la adecuada configuraci�n se
 establece el la phpmussel.ini archivo (cleanup debe estar desactivado), y
 cuando hecho, en un PHP archivo conectado a phpMussel, utilice la siguiente
 funci�n en su c�digo:

 phpMussel($what_to_scan,$output_type,$output_flatness);

 D�nde:
  - $what_to_scan es una cadena o una array, apuntando a un destino archivo, un
   destino directorio o un array de destinos archivos y/o destinos directorios.
 - $output_type es un entero, indicando el formato en el que los resultados son
   para estar de regreso como. Un valor de 0 indica a la funci�n para devolver
   resultados como un entero (un resultado devuelto de -2 indica que se ha
   corruptos datos detectados durante el escanear y por lo tanto el escanear no
   pudo completar, -1 indica que las extensiones o complementos requeridos por
   php para ejecutar el escaneo faltaban y por lo tanto el escanear no pudo
   completar, 0 indica que la escanear objetivo no existe y por lo tanto no
   hab�a nada para escanear, 1 indica que el objetivo fue escaneado con �xito
   y no se detectaron problemas, y 2 indica que el objetivo fue escaneado con
   �xito y se detectaron problemas). Un valor de 1 instruye la funci�n a
   devuelva resultados como texto legible por humanos. Un valor de 2 instruye
   la funci�n ambos a devuelva resultados como texto legible por humanos y a
   exportar los resultados a una global variable. Esta variable es opcional,
   predefinido como 0.
 - $output_flatness es un entero, indicando si se permite a los resultados que
   se devuelven como un array o no. Normalmente, si la escanear objetivo
   contenida varios art�culos (por ejemplo, si un directorio o array) los
   resultados se devuelven en un array (valor predefinido de 0). Un valor de 1
   instruye la funci�n implosionar cualquier array antes de la entrada,
   resultando en una aplanada cadena que contiene los resultados a devolver.
   Esta variable es opcional, predefinido como 0.

 Ejemplos:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Devuelve algo como esto (como una cadena):
    Wed, 16 Sep 2013 02:49:46 +0000 Iniciado.
    > Verificando '/user_name/public_html/my_file.html':
    -> No problemas encontrado.
    Wed, 16 Sep 2013 02:49:47 +0000 Terminado.

 Para una descripci�n completa del tipo de firmas phpMussel utiliza durante el
 escanear y la forma en que maneja estas firmas, consulte la secci�n Firma
 Formatos de este README archivo.

 Si se encuentra alg�n falsos positivos, si se encuentra con algo nuevo que
 crees que deber�a ser bloqueada, o para cualquier otra cosa en relaci�n con
 las firmas, por favor contacto conmigo al respecto para que pueda hacer los
 cambios necesarios, para que, si no se comunica conmigo, posiblemente no
 necesariamente tener en cuenta.

 Para desactivar las firmas que se incluyen con phpMussel (por ejemplo, si
 usted est� experimentando un falso positivo espec�fico para sus prop�sitos
 que normalmente no deber�a ser suprimido), consulte las notas de la Greylist
 en el Navegador Comandos secci�n de este README archivo.

 Adem�s del escaneo de archivos cargas y la opcional escaneo de otros archivos
 y/o directorios especificados a trav�s de la funci�n anterior, incluido en
 phpMussel es una funci�n con el prop�sito para escanear el cuerpo de los email
 mensajes. Esta funci�n se comporta de manera similar del est�ndar phpMussel()
 funci�n, excepto centra �nicamente contra las email basadas ClamAV firmas. No
 he conectada estas firmas en el est�ndar phpMussel() funci�n, debido a que es
 improbable que usted encontrar el cuerpo de un entrante email mensaje en la
 necesidad el escaneo dentro un archivo carga dirigido a una p�gina donde
 phpMussel est� conectado, y por lo tanto, para conectar estas firmas en la
 phpMussel() funci�n ser�a redundante. Pero, dicho esto, si tener una separada
 funci�n contra estas firmas podr�a ser muy �til por algunos, especialmente por
 aquellos cuyos CMS o web sistema est� conectado de alguna manera en su email
 sistema y para aquellos de los cuales analizar sus email mensajes a trav�s de
 una php script de los que potencialmente podr�an conectar en phpMussel.
 Configuraci�n para esta funci�n, como todos los dem�s, es controlado a trav�s
 de phpmussel.ini archivo. Para utilizar esta funci�n (va necesita para hacer
 su propia implementaci�n), en una php archivo que est� conectado a phpMussel,
 utilizar la siguiente funci�n en el c�digo:

 phpMussel_mail($cuerpo);

 Donde $cuerpo es el cuerpo del email mensaje que desea escanear (adem�s,
 podr�a intentar escanear nuevos mensajes en su foro, los mensajes entrantes de
 su online contacto form o similar). Si se produce alg�n error que impide la
 funci�n de completar su escanear, valor de -1 ser�n devueltos. Si la funci�n
 completa su escanear y no encuentra nada, valor de 0 ser�n devueltos (que
 significa es limpio). Pero, si la funci�n encontrar algo, una string ser�
 devuelta contiene un mensaje declarando lo que ha encontrado.

 Adem�s de lo anterior, si nos fijamos en el c�digo fuente, es posible que
 observe las funciones phpMusselD() y phpMusselR(). Estas funciones son
 subfunciones de phpMussel(), y no debe ser llamado directamente fuera de esa
 madre funci�n (no a causa de adversos efectos.. M�s, porque no servir�a
 cualquier prop�sito, y probablemente no ser� en realidad funcione
 correctamente).

 Hay muchos otros controles y funciones disponibles dentro phpMussel para su
 uso, tambi�n. Para cualquier controles y funciones para los cuales, para el
 final de esta secci�n del README, todav�a no se han documentado, por favor
 siga leyendo y se refieren a los Navegador Comandos secci�n de este README
 archivo.

                                     ~ ~ ~


 3B. C�MO USO (PARA CLI)

 Por favor, consulte la secci�n "C�MO INSTALAR (PARA CLI)" de este README.

 Tenga en cuenta que, aunque las futuras versiones de phpMussel deben apoyar
 otros sistemas, en este momento, phpMussel CLI modo compatibilidad s�lo est�
 optimizado para su uso en sistemas basados en Windows (por supuesto, usted
 puede probarlo en otros sistemas, pero no puedo garantizar que va funcionar
 como es debido).

 Tambi�n tenga en cuenta que phpMussel no es el funcional equivalente de una
 completa anti-virus suite, y no como convencionales anti-virus suites, no
 supervisa la memoria activa o detectar virus fuera del alcance de su acceso!
 Es s�lo detecta virus contenidos en los archivos espec�ficos expl�citamente
 para escaneo.

                                     ~ ~ ~


 4A. NAVEGADOR COMANDOS

 Cuando phpMussel est� instalado y funciona correctamente en su sistema, si ha
 configurado las variables script_password y logs_password en la configuraci�n
 archivo, usted ser� capaz de realizar un limitado n�mero de administrativas
 funciones y entrar de un n�mero de comandos a phpMussel trav�s de su
 navegador. La raz�n de estas contrase�as deben definida a fin de que estos
 navegador controles es para garantizar adecuada seguridad, adecuada protecci�n
 para estos navegador controles y para asegurar que existe una manera para
 estos navegador controles estar deshabilitado en su totalidad si no se desean
 por usted y/o otros webmasters/administradores usar phpMussel. Por lo tanto,
 en otras palabras, para permitir estos controles, definir un contrase�a, y
 para desactivar estos controles, no definir ninguna contrase�a.
 Alternativamente, si usted decide habilitar estos controles y luego optar
 desactivar estos controles en una fecha posterior, hay un comando para hacerlo
 (tal puede ser �til si realiza algunas acciones que usted se sienta
 potencialmente podr�an comprometer las contrase�as delegadas y necesitas de
 desactivar r�pidamente estos controles sin modificar la configuraci�n
 archivo).

 Algunas de las razones por las que -debe- permitir estos controles:
 - Proporciona una f�cil manera de greylist firmas en casos tales como cuando
   se descubre una firma que se produce un falso positivo mientras que cargar
   archivos a su sistema y usted no tiene tiempo para editar manualmente y
   recargar su archivo de greylist firmas.
 - Proporciona una f�cil manera de usted permite que alguien no sea usted para
   controlar su copia de phpMussel sin el impl�cita necesidad de concederles
   acceso a FTP.
 - Proporciona una f�cil manera para proporcionar acceso controlado a los
   registros archivos.
 - Proporciona una f�cil manera para actualizar phpMussel cuando haya
   actualizaciones disponibles.
 - Proporciona una f�cil manera para monitorizar phpMussel cuando el FTP acceso
   u otros puntos de convencional acceso para el monitoreo de phpMussel no
   est�n disponibles.

 Algunas de las razones por las que -no- debe permitir estos controles:
 - Proporciona un vector para atacantes y indeseables para determinar si se o
   no que est� utilizando phpMussel (aunque, esto podr�a ser una raz�n de
   apoyar y/o una raz�n contra, dependiendo de la perspectiva) por forma de
   enviar ciegas comandos a los servidores como una forma de sondear. Por un
   lado, esto podr�a desalentar atacantes de la focalizaci�n de su sistema si
   se enteran de que est� utilizando phpMussel, suponiendo que se est�n
   sondando porque su m�todo de ataque es ineficaz como resultado del uso de
   phpMussel. En el otro lado, si alg�n imprevisto y desconoce en la actualidad
   explotan dentro phpMussel o una versi�n futura del mismo sale a la luz, y si
   podr�a potencialmente proporcionar un vector de ataque, un resultado
   positivo de tal sondando podr�a alentar atacantes para la focalizaci�n de su
   sistema.
 - Si sus contrase�as delegados fueron en alguna vez comprometidos, menos que
   se modifiquen, podr�a proporcionar una manera para que un atacante para
   eludir cualquier firmas puede ser de otra manera normalmente prevenir sus
   ataques tengan �xito, o potencialmente desactivar phpMussel enteramente, as�
   proporcionando una manera de hacer que la eficacia de phpMussel nulo y sin
   efecto.

 De cualquier manera, independientemente de lo que elija, la elecci�n es en
 �ltima instancia el tuyo. Por norma, estos controles se desactivan, pero
 tienen un pensar en ello, y si decide que los quiere, esta secci�n se explica
 c�mo habilitar ellos y c�mo usarlos.

 Una lista de los comandos disponibles del navegador:

 scan_log
   Contrase�a necesario: logs_password
   Otros requisitos: scan_log necesario ser definido.
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?logspword=[logs_password]&phpmussel=scan_log
   ~
   Qu� hace: Imprime el contenido de su scan_log archivo a la pantalla.
   ~
 scan_kills
   Contrase�a necesario: logs_password
   Otros requisitos: scan_kills necesario ser definido.
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?logspword=[logs_password]&phpmussel=scan_kills
   ~
   Qu� hace: Imprime el contenido de su scan_kills archivo a la pantalla.
   ~
 controls_lockout
   Contrase�a necesario: logs_password O script_password
   Otros requisitos: (nada)
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Example 1: ?logspword=[logs_password]&phpmussel=controls_lockout
   Example 2: ?pword=[script_password]&phpmussel=controls_lockout
   ~
   Qu� hace: Desactiva todos los controles del navegador. Esto se debe utilizar
             si sospecha que alguna de las contrase�as se han comprometido
             (esto puede ocurrir si usted est� utilizando estos controles desde
             un computadora que no es de confianza y/o no es seguro).
             controls_lockout funciones mediante la creaci�n de un archivo,
             controls.lck, en su vault, que phpMussel comprobar� antes de
             realizar cualquier comandos de ning�n tipo. Cuando esto sucede,
             para reactivar estos controles, tendr� que suprimir manualmente la
             controls.lck archivo a trav�s de FTP o similar. Puede ser llamado
             usando cualquiera de las contrase�as.
   ~
 disable
   Contrase�a necesario: script_password
   Otros requisitos: (nada)
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=disable
   ~
   Qu� hace: Desactivar phpMussel. Esto debe ser utilizar si usted est�
             realizando cualquier actualizaciones o cambios en su sistema o si
             usted est� instalar cualquier nuevo software o m�dulos para su
             sistema que potencialmente podr�an o hacer desencadenar falsos
             positivos. Esto tambi�n debe usar si usted est� teniendo problemas
             con phpMussel pero no desean eliminarlo de su sistema. Si esto
             sucede, para reactivar phpMussel, usar "enable".
   ~
 enable
   Contrase�a necesario: script_password
   Otros requisitos: (nada)
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=enable
   ~
   Qu� hace: Activar phpMussel. Esto debe ser utilizar si usted ha desactivado
             anteriormente phpMussel usando "disable" y quiere reactivarla.
   ~
 update
   Contrase�a necesario: script_password
   Otros requisitos: update.dat and update.inc must exist.
   Par�metros necesarios: (nada)
   Par�metros opcionales: forcedupdate
   Ejemplo: ?pword=[script_password]&phpmussel=update&musselvar=forcedupdate
   ~
   Qu� hace: Comprobar por actualizaciones para ambos phpMussel y sus firmas.
             Si las actualizaciones comprobar tienen �xito y actualizaciones
             est� encuentran, intentar� descargar e instalar estas
             actualizaciones. Si las actualizaciones se comprueban demasiado
             r�pido, actualizaciones comprobar abortar�. Si las actualizaciones
             comprobar fallan, actualizaciones comprobar abortar�. Si el
             opcional par�metro "forcedupdate" se suministra, el tiempo de la
             �ltima actualizaci�n ser� ignorado y por lo tanto actualizaciones
             comprobar continuar� incluso si est� ser comprobando "demasiado
             r�pido", pero a�n as�, abortar� si actualizaciones comprobar
             fallan. Los resultados de todo el proceso se imprimen en la
             pantalla. Recomiendo incluyendo el opcional par�metro
             "forcedupdate" si usted est� desencadenando manualmente este
             control, pero por favor, no use "forcedupdate" si est�
             automatizando el proceso, como por ejemplo a trav�s de cron o
             similar. Recomiendo comprobar al menos una vez por mes para
             asegurar que sus firmas y su copia de phpMussel se mantienen
             actualizada (a menos que, naturalmente, usted est� comprobando las
             actualizaciones e instalandolos manualmente, que, aun as� sigo
             recomendando hacer al menos uno por mes). Comprobar m�s de dos
             veces por mes es probablemente in�til, en consideraci�n que (en el
             momento de escribir este) estoy trabajando en este proyecto solo y
             estoy muy improbable de ser capaz de producir actualizaciones de
             cualquier tipo con m�s frecuencia que la (ni tengo particular
             quiero para hacerlo en la mayor parte).
   ~
 greylist
   Contrase�a necesario: script_password
   Otros requisitos: (nada)
   Par�metros necesarios: [Nombre de la firma para la greylist]
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=greylist&musselvar=[Signature]
   ~
   Qu� hace: Agregar una firma a la greylist.
   ~
 greylist_clear
   Contrase�a necesario: script_password
   Otros requisitos: (nada)
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=greylist_clear
   ~
   Qu� hace: Borrar toda de la greylist.
   ~
 greylist_show
   Contrase�a necesario: script_password
   Otros requisitos: (nada)
   Par�metros necesarios: (nada)
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=greylist_show
   ~
   Qu� hace: Imprime el contenido de la greylist a la pantalla.
   ~

                                     ~ ~ ~


 4B. CLI (COMANDOS L�NEA INTERFAZ)

 phpMussel se puede ejecutar como un interactivo archivos esc�ner en CLI modo
 dentro sistemas basados en Windows. Consulte el "C�MO INSTALAR (PARA CLI)"
 secci�n de este readme archivo para m�s detalles.

 Para obtener una lista de los disponibles CLI comandos, para el CLI aviso,
 escribir 'c', y pulse Enter.

                                     ~ ~ ~


 5. ARCHIVOS INCLUIDOS EN ESTE PAQUETE

 La siguiente es una lista de todos los archivos que deber�a haberse incluido
 en el archivado copia de este script cuando descargado, todos los archivos
 que pueden ser potencialmente creados como resultado de su uso de este script,
 junto con una breve descripci�n de lo que todos estos archivos son para.

 /phpmussel.php (Script, Incluido)
    phpMussel Cargador archivo. Carga la principal script, actualizador,
    etc�tera. Esto es lo que se supone debe enganchando (esencial)!
    ~
 /web.config (Otro, Incluido)
    Un ASP.NET configuraci�n archivo (en este caso, para proteger la "/vault"
    directorio contra el acceso de fuentes no autorizadas en el caso de que la
    script est� instalado en un servidor basado en ASP.NET tecnolog�as).
    ~
 /_docs/ (Directorio)
    Documentaci�n directorio (contiene varios archivos).
    ~
 /_docs/change_log.txt (Documentaci�n, Incluido)
    Un registro de los cambios realizados en la principal script entre las
    diferentes versiones (no se requiere para lo adecuado funcionamiento de la
    script).
    ~
 /_docs/readme.DE.txt (Documentaci�n, Incluido); DEUTSCH
 /_docs/readme.EN.txt (Documentaci�n, Incluido); ENGLISH
 /_docs/readme.ES.txt (Documentaci�n, Incluido); ESPA�OL
 /_docs/readme.FR.txt (Documentaci�n, Incluido); FRAN�AIS
 /_docs/readme.ID.txt (Documentaci�n, Incluido); BAHASA INDONESIA
 /_docs/readme.IT.txt (Documentaci�n, Incluido); ITALIANO
 /_docs/readme.NL.txt (Documentaci�n, Incluido); NEDERLANDSE
 /_docs/readme.PT.txt (Documentaci�n, Incluido); PORTUGU�S
    La README archivos (por ejemplo; el archivo que est�s leyendo).
    ~
 /_docs/signatures_tally.txt (Documentaci�n, Incluido)
    Cifra neta de cambio de las incluidas firmas (no se requiere para lo
    adecuado funcionamiento de la script).
    ~
 /_testfiles/ (Directorio)
    Prueba archivos directorio (contiene varios archivos).
    Todos los archivos contenidos son prueba archivos para probando si
    phpMussel ha sido instalado correctamente en su sistema, y que no es
    necesario cargar este directorio o cualquiera de sus archivos excepto
    cuando haciendo tales pruebas.
    ~
 /_testfiles/ascii_standard_testfile.txt (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel normalizado ASCII firmas.
    ~
 /_testfiles/coex_testfile.rtf (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel Complejo Extendido firmas.
    ~
 /_testfiles/exe_standard_testfile.exe (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel PE firmas.
    ~
 /_testfiles/general_standard_testfile.txt (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel generales firmas.
    ~
 /_testfiles/graphics_standard_testfile.gif (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel gr�ficas firmas.
    ~
 /_testfiles/html_standard_testfile.txt (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel normalizado HTML firmas.
    ~
 /_testfiles/md5_testfile.txt (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel MD5 firmas.
    ~
 /_testfiles/metadata_testfile.txt.gz (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel metadatos firmas y para probando GZ
    archivo apoyo en su sistema.
    ~
 /_testfiles/metadata_testfile.zip (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel metadatos firmas y para probando ZIP
    archivo apoyo en su sistema.
    ~
 /_testfiles/ole_testfile.ole (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel OLE firmas.
    ~
 /_testfiles/pdf_standard_testfile.pdf (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel PDF firmas.
    ~
 /_testfiles/pe_sectional_testfile.exe (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel PE Secci�nal firmas.
    ~
 /_testfiles/xdp_standard_testfile.xdp (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel XML/XDP-Chunk firmas.
    ~
 /vault/ (Directorio)
    Vault directorio (contiene varios archivos).
    ~
 /vault/quarantine/ (Directorio)
    Cuarentena directorio (contiene los cuarentenadas archivos).
    ~
 /vault/quarantine/.htaccess (Otro, Incluido)
    Un hipertexto acceso archivo (en este caso, para proteger confidenciales
    archivos perteneciente a la script contra el acceso de fuentes no
    autorizadas).
    ~
 /vault/.htaccess (Otro, Incluido)
    Un hipertexto acceso archivo (en este caso, para proteger confidenciales
    archivos perteneciente a la script contra el acceso de fuentes no
    autorizadas).
    ~
 /vault/ascii_clamav_regex.cvd (Firmas, Incluidos)
 /vault/ascii_clamav_regex.map (Firmas, Incluidos)
 /vault/ascii_clamav_standard.cvd (Firmas, Incluidos)
 /vault/ascii_clamav_standard.map (Firmas, Incluidos)
 /vault/ascii_custom_regex.cvd (Firmas, Incluidos)
 /vault/ascii_custom_standard.cvd (Firmas, Incluidos)
 /vault/ascii_mussel_regex.cvd (Firmas, Incluidos)
 /vault/ascii_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para normalizados ASCII firmas.
    Requerido si la opci�n de normalizados ASCII firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/coex_clamav.cvd (Firmas, Incluidos)
 /vault/coex_custom.cvd (Firmas, Incluidos)
 /vault/coex_mussel.cvd (Firmas, Incluidos)
    Archivos para Complejo Extendido firmas.
    Requerido si la opci�n de Complejo Extendido firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/elf_clamav_regex.cvd (Firmas, Incluidos)
 /vault/elf_clamav_regex.map (Firmas, Incluidos)
 /vault/elf_clamav_standard.cvd (Firmas, Incluidos)
 /vault/elf_clamav_standard.map (Firmas, Incluidos)
 /vault/elf_custom_regex.cvd (Firmas, Incluidos)
 /vault/elf_custom_standard.cvd (Firmas, Incluidos)
 /vault/elf_mussel_regex.cvd (Firmas, Incluidos)
 /vault/elf_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para ELF firmas.
    Requerido si la opci�n de ELF firmas en phpmussel.ini est� habilitado. Se
    puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/exe_clamav_regex.cvd (Firmas, Incluidos)
 /vault/exe_clamav_regex.map (Firmas, Incluidos)
 /vault/exe_clamav_standard.cvd (Firmas, Incluidos)
 /vault/exe_clamav_standard.map (Firmas, Incluidos)
 /vault/exe_custom_regex.cvd (Firmas, Incluidos)
 /vault/exe_custom_standard.cvd (Firmas, Incluidos)
 /vault/exe_mussel_regex.cvd (Firmas, Incluidos)
 /vault/exe_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para Port�til Ejecutable firmas.
    Requerido si la opci�n de EXE firmas en phpmussel.ini est� habilitado. Se
    puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/filenames_clamav.cvd (Firmas, Incluidos)
 /vault/filenames_custom.cvd (Firmas, Incluidos)
 /vault/filenames_mussel.cvd (Firmas, Incluidos)
    Archivos para archivo nombre firmas.
    Requerido si la opci�n de filename firmas en phpmussel.ini est� habilitado.
    Se puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/general_clamav_regex.cvd (Firmas, Incluidos)
 /vault/general_clamav_regex.map (Firmas, Incluidos)
 /vault/general_clamav_standard.cvd (Firmas, Incluidos)
 /vault/general_clamav_standard.map (Firmas, Incluidos)
 /vault/general_custom_regex.cvd (Firmas, Incluidos)
 /vault/general_custom_standard.cvd (Firmas, Incluidos)
 /vault/general_mussel_regex.cvd (Firmas, Incluidos)
 /vault/general_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para generales firmas.
    Requerido si la opci�n de generales firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/graphics_clamav_regex.cvd (Firmas, Incluidos)
 /vault/graphics_clamav_regex.map (Firmas, Incluidos)
 /vault/graphics_clamav_standard.cvd (Firmas, Incluidos)
 /vault/graphics_clamav_standard.map (Firmas, Incluidos)
 /vault/graphics_custom_regex.cvd (Firmas, Incluidos)
 /vault/graphics_custom_standard.cvd (Firmas, Incluidos)
 /vault/graphics_mussel_regex.cvd (Firmas, Incluidos)
 /vault/graphics_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para gr�ficas firmas.
    Requerido si la opci�n de gr�ficas firmas en phpmussel.ini est� habilitado.
    Se puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/greylist.csv (Firmas, Incluidos/Creados)
    CSV de las firmas en la Greylist indicando para phpMussel las firmas que
    deben ser ignorados (file automatically recreated if deleted).
    ~
 /vault/hex_general_commands.csv (Firmas, Incluidos)
    Hex-codificado CSV de generales comandos detecciones opcionalmente
    utilizado por phpMussel. Requerido si la opci�n de generales comandos
    detecciones en phpmussel.ini est� habilitado. Se puede eliminarlo si la
    opci�n est� desactivada (pero los archivos ser� recreado durante
    actualizaci�ns).
    ~
 /vault/html_clamav_regex.cvd (Firmas, Incluidos)
 /vault/html_clamav_regex.map (Firmas, Incluidos)
 /vault/html_clamav_standard.cvd (Firmas, Incluidos)
 /vault/html_clamav_standard.map (Firmas, Incluidos)
 /vault/html_custom_regex.cvd (Firmas, Incluidos)
 /vault/html_custom_standard.cvd (Firmas, Incluidos)
 /vault/html_mussel_regex.cvd (Firmas, Incluidos)
 /vault/html_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para normalizados HTML firmas.
    Requerido si la opci�n de normalizados HTML firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/lang.inc (Script, Incluido)
    phpMussel Ling��sticos datos; Requerido para multiling�es capacidades.
    ~
 /vault/macho_clamav_regex.cvd (Firmas, Incluidos)
 /vault/macho_clamav_regex.map (Firmas, Incluidos)
 /vault/macho_clamav_standard.cvd (Firmas, Incluidos)
 /vault/macho_clamav_standard.map (Firmas, Incluidos)
 /vault/macho_custom_regex.cvd (Firmas, Incluidos)
 /vault/macho_custom_standard.cvd (Firmas, Incluidos)
 /vault/macho_mussel_regex.cvd (Firmas, Incluidos)
 /vault/macho_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para Mach-O firmas.
    Requerido si la opci�n de Mach-O firmas en phpmussel.ini est� habilitado.
    Se puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/mail_clamav_regex.cvd (Firmas, Incluidos)
 /vault/mail_clamav_regex.map (Firmas, Incluidos)
 /vault/mail_clamav_standard.cvd (Firmas, Incluidos)
 /vault/mail_clamav_standard.map (Firmas, Incluidos)
 /vault/mail_custom_regex.cvd (Firmas, Incluidos)
 /vault/mail_custom_standard.cvd (Firmas, Incluidos)
 /vault/mail_mussel_regex.cvd (Firmas, Incluidos)
 /vault/mail_mussel_standard.cvd (Firmas, Incluidos)
 /vault/mail_mussel_standard.map (Firmas, Incluidos)
    Los archivos para las firmas utilizadas por la funci�n phpMussel_mail().
    Requerido si la funci�n phpMussel_mail() se utilizado de cualquiera manera.
    Se puede eliminarlo si no se utilizado (pero los archivos ser� recreado
    durante actualizaci�ns).
    ~
 /vault/md5_clamav.cvd (Firmas, Incluidos)
 /vault/md5_custom.cvd (Firmas, Incluidos)
 /vault/md5_mussel.cvd (Firmas, Incluidos)
    Archivos para MD5 basadas firmas.
    Requerido si la opci�n de MD5 basadas firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/metadata_clamav.cvd (Firmas, Incluidos)
 /vault/metadata_custom.cvd (Firmas, Incluidos)
 /vault/metadata_mussel.cvd (Firmas, Incluidos)
    Archivos para archivo metadatos firmas.
    Requerido si la opci�n de archivo metadatos firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/ole_clamav_regex.cvd (Firmas, Incluidos)
 /vault/ole_clamav_regex.map (Firmas, Incluidos)
 /vault/ole_clamav_standard.cvd (Firmas, Incluidos)
 /vault/ole_clamav_standard.map (Firmas, Incluidos)
 /vault/ole_custom_regex.cvd (Firmas, Incluidos)
 /vault/ole_custom_standard.cvd (Firmas, Incluidos)
 /vault/ole_mussel_regex.cvd (Firmas, Incluidos)
 /vault/ole_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para OLE firmas.
    Requerido si la opci�n de OLE firmas en phpmussel.ini est� habilitado. Se
    puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/pdf_clamav_regex.cvd (Firmas, Incluidos)
 /vault/pdf_clamav_regex.map (Firmas, Incluidos)
 /vault/pdf_clamav_standard.cvd (Firmas, Incluidos)
 /vault/pdf_clamav_standard.map (Firmas, Incluidos)
 /vault/pdf_custom_regex.cvd (Firmas, Incluidos)
 /vault/pdf_custom_standard.cvd (Firmas, Incluidos)
 /vault/pdf_mussel_regex.cvd (Firmas, Incluidos)
 /vault/pdf_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para PDF firmas.
    Requerido si la opci�n de PDF firmas en phpmussel.ini est� habilitado. Se
    puede eliminarlo si la opci�n est� desactivada (pero los archivos ser�
    recreado durante actualizaci�ns).
    ~
 /vault/pe_clamav.cvd (Firmas, Incluidos)
 /vault/pe_custom.cvd (Firmas, Incluidos)
 /vault/pe_mussel.cvd (Firmas, Incluidos)
    Archivos para PE Secci�nal firmas.
    Requerido si la opci�n de PE Secci�nal firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/phpmussel.inc (Script, Incluido)
    phpMussel N�cleo Script; La principal cuerpo de phpMussel (esencial)!
    ~
 /vault/phpmussel.ini (Otro, Incluido)
    phpMussel Configuraci�n archivo; Contiene todas las configuraci�n opciones
    para phpMussel, instruyendo para qu� hacer y c�mo operar correctamente
    (esencial)!
    ~
 /vault/scan_log.txt *(Log archivo, Creado)
    Un registro de todo escaneada por phpMussel.
    ~
 /vault/scan_kills.txt *(Log archivo, Creado)
    Un registro de todos archivos cargas bloqueado/asesinado por phpMussel.
    ~
 /vault/swf_clamav_regex.cvd (Firmas, Incluidos)
 /vault/swf_clamav_regex.map (Firmas, Incluidos)
 /vault/swf_clamav_standard.cvd (Firmas, Incluidos)
 /vault/swf_clamav_standard.map (Firmas, Incluidos)
 /vault/swf_custom_regex.cvd (Firmas, Incluidos)
 /vault/swf_custom_standard.cvd (Firmas, Incluidos)
 /vault/swf_mussel_regex.cvd (Firmas, Incluidos)
 /vault/swf_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para Shockwave firmas.
    Requerido si la opci�n de Shockwave firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/template.html (Otro, Incluido)
    phpMussel Template archivo; Template para HTML salida producida por
    phpMussel por sus bloqueados cargas archivos mensaje (el mensaje visto por
    el cargador).
    ~
 /vault/update.dat (Otro, Incluido)
    Archivo que contiene la versi�n informaci�n tanto para la phpMussel script
    y para la phpMussel firmas. Si alguna vez desea actualizar autom�ticamente
    phpMussel o desea actualizar phpMusel trav�s de su navegador, este archivo
    es esencial.
    ~
 /vault/update.inc (Script, Incluido)
    phpMussel Actualizaci�n Script; Requerido para autom�ticas actualizaciones
    y para actualizando phpMussel trav�s de su navegador, pero no es requerido
    por lo dem�s.
    ~
 /vault/whitelist_clamav.cvd (Firmas, Incluidos)
 /vault/whitelist_custom.cvd (Firmas, Incluidos)
 /vault/whitelist_mussel.cvd (Firmas, Incluidos)
    Archivo espec�fico whitelist.
    Requerido si la opci�n para la whitelist en phpmussel.ini est� habilitado y
    si usted desea tener espec�ficos archivos en la whitelist. Se puede
    eliminarlo si la opci�n est� desactivada o si usted no requiere de la
    whitelist (pero los archivos ser� recreado durante actualizaci�ns).
    ~
 /vault/xmlxdp_clamav_regex.cvd (Firmas, Incluidos)
 /vault/xmlxdp_clamav_regex.map (Firmas, Incluidos)
 /vault/xmlxdp_clamav_standard.cvd (Firmas, Incluidos)
 /vault/xmlxdp_clamav_standard.map (Firmas, Incluidos)
 /vault/xmlxdp_custom_regex.cvd (Firmas, Incluidos)
 /vault/xmlxdp_custom_standard.cvd (Firmas, Incluidos)
 /vault/xmlxdp_mussel_regex.cvd (Firmas, Incluidos)
 /vault/xmlxdp_mussel_standard.cvd (Firmas, Incluidos)
    Archivos para XML/XDP-Chunk firmas.
    Requerido si la opci�n de XML/XDP-Chunk firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada (pero los
    archivos ser� recreado durante actualizaci�ns).
    ~

 * Nombre del archivo puede variar basado de las estipulaciones de
   configuraci�n (en phpmussel.ini).

 = RESPECTO A FIRMAS ARCHIVOS =
    CVD es un acr�nimo de "ClamAV Virus Definiciones", en referencia tanto a
    c�mo ClamAV se refiere a sus propias firmas y al uso de esas firmas para
    phpMussel; Los archivos que terminan en "CVD" contienen firmas.
    ~
    Los archivos que terminan en "MAP" instruyen phpMussel con respecto a las
    firmas que debe y no debe utilizarse para individuales escaneos; No todas
    las firmas se necesariamente requieren para cada individual escaneo, as�,
    phpMussel utiliza mapas de los firmas archivos para acelerar el escaneo
    proceso (un proceso que, alternativamente, ser�a extremadamente lento y
    tedioso).
    ~
    Firmas archivos marcados con "_regex" contienen firmas utilizando regulares
    expresiones patrones (regex).
    ~
    Firmas archivos marcados con "_standard" contienen firmas que
    espec�ficamente no utiliza ning�n tipo de patrones.
    ~
    Firmas archivos marcados con no "_regex" ni "_standard" ser� como uno o el
    otro, pero no ambos (consulte la FIRMA FORMATOS secci�n de este README
    archivo para la documentaci�n y espec�ficos detalles).
    ~
    Firmas archivos marcados con "_clamav" contienen firmas que se obtenido
    enteramente de la base de datos de ClamAV (GNU/GPL).
    ~
    Firmas archivos marcados con "_custom", por predefinido, no contienen
    cualquiera firmas; Existen estos dichos archivos para darle un lugar para
    colocar sus propios personalizadas firmas, si viene con cualquiera de su
    propia.
    ~
    Firmas archivos marcados con "_mussel" contienen firmas que se obtenido
    espec�ficamente no desde ClamAV, firmas que, en general, uno u otro, yo
    mismo he escrito y/o basado en la informaci�n obtenida de diversas fuentes.
    ~

                                     ~ ~ ~


 6. CONFIGURACI�N OPCIONES

 La siguiente es una lista de variables encuentran en la "phpmussel.ini"
 configuraci�n archivo de phpMussel, junto con una descripci�n de sus
 prop�sito y funci�n.

 "general" (Categor�a)
 - General configuraci�n para phpMussel.
    "script_password"
    - Por la conveniencia, phpMussel permitir� ciertas funciones (incluyendo la
      capacidad de actualizar phpMussel) para ser desencadenado manualmente a
      trav�s de POST, GET y QUERY. Pero dicho esto, como medida de seguridad,
      para hacer esto, phpMussel esperar� una contrase�a ser�n incluido con el
      comando, como para asegurarse de que usted es, y no otra persona,
      intentando desencadenar manualmente estas funciones. Definir
      script_password a cualquier contrase�a que desea utilizar. Si no
      contrase�a se define, desencadenando manualmente desactivar� por
      predefinido. Utilice algo que recordar� pero que se dif�cil de adivinar
      para otros.
      * No tiene influencia en CLI modo.
    "logs_password"
    - El mismo como script_password, pero para ver el contenido de scan_log y
      scan_kills. Tener contrase�as separado puede ser �til si usted desea dar
      alguna otra persona acceso a un conjunto de funciones, pero no el otro.
      * No tiene influencia en CLI modo.
    "cleanup"
    - Despejar la script variables y la cach� despu�s de la ejecuci�n. Si usted
      no est� utilizando la script m�s all� de inicial escaneando de archivos
      cargas, debe definir como s�, para minimizar el uso de memoria. Si usted
      est� utilizando la script para prop�sitos m�s all� de inicial escaneando
      de archivos cargas, debe definir como no, para evitar recargar
      innecesariamente duplicados datos en la memoria. En general pr�ctica,
      probablemente deber�a definirse como s�, pero, si usted hace esto, usted
      no ser� capaz de utilizar la script para cualquier cosa otro que de
      escaneando archivos cargas.
      * No tiene influencia en CLI modo.
    "scan_log"
    - Nombre del archivo para registrar todos los resultados de la escaneo en.
      Especifique un archivo nombre, o dejar en blanco para desactivar.
    "scan_kills"
    - Nombre del archivo para registrar todos bloqueados o matados cargas en.
      Especifique un archivo nombre, o dejar en blanco para desactivar.
    "ipaddr"
    - D�nde encontrar el IP direcci�n de la conectando request? (�til para
      servicios como Cloudflare y tales) Predefinido = REMOTE_ADDR
      AVISO: No cambie esto a menos que sepas lo que est�s haciendo!
    "forbid_on_block"
    - Deber�a phpMussel enviar 403 header con la bloqueados archivos cargas
      mensaje, o quedarse con los usual 200 OK?
      0 = No (200) [Predefinido], 1 S� (403).
    "delete_on_sight"
    - Enabling this directive will instruct the script to attempt to
      immediately delete any scanned attempted file upload matching any
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
    "quarantine_key"
    - phpMussel is able to quarantine flagged attempted file uploads in
      isolation within the phpMussel vault, if this is something you want it to
      do. Casual users of phpMussel of which simply wish to protect their
      websites or hosting environment without having any interest in deeply
      analysing any flagged attempted file uploads should leave this
      functionality disabled, but any users interested in further analysis of
      flagged attempted file uploads for malware research or for similar such
      things should enable this functionality. Quarantining of flagged
      attempted file uploads can sometimes also assist in debugging
      false-positives, if this is something that frequently occurs for you. To
      disable quarantine functionality, simply leave the "quarantine_key"
      directive empty, or erase the contents of that directive if it isn't
      already empty. To enable quarantine functionality, enter some value into
      the directive. The "quarantine_key" is an important security feature of
      the quarantine functionality required as a means of preventing the
      quarantine functionality from being exploited by potential attackers and
      as a means of preventing any potential execution of data stored within
      the quarantine. The "quarantine_key" should be treated in the same manner
      as your passwords: The longer the better, and guard it tightly. For best
      effect, use in conjunction with "delete_on_sight".
    "quarantine_max_filesize"
    - The maximum allowable filesize of files to be quarantined. Files larger
      than the value specified below will NOT be quarantined. This directive is
      important as a means of making it more difficult for any potential
      attackers to flood your quarantine with unwanted data potentially causing
      run-away data usage on your hosting service. Value is in KB.
      Default =2048 =2048KB =2MB.
    "quarantine_max_usage"
    - The maximum memory usage allowed for the quarantine. If the total memory
      used by the quarantine reaches this value, the oldest quarantined files
      will be deleted until the total memory used no longer reaches this value.
      This directive is important as a means of making it more difficult for
      any potential attackers to flood your quarantine with unwanted data
      potentially causing run-away data usage on your hosting service.
      Value is in KB. Default =65536 =65536KB =64MB.
    "honeypot_mode"
    - When honeypot mode is enabled, phpMussel will attempt to quarantine every
      single file upload that it encounters, regardless of whether or not the
      file being uploaded matches any included signatures, and no actual
      scanning or analysis of those attempted file uploads will actually occur.
      This functionality should be useful for those that wish to use phpMussel
      for the purposes of virus/malware research, but it is neither recommended
      to enable this functionality if the intended use of phpMussel by the user
      is for actual file upload scanning nor is it recommended to use the
      honeypot functionality for purposes other than honeypotting. By default,
      this option is disabled. 0 = Disabled [Default], 1 = Enabled.
 "signatures" (Categor�a)
 - Configuration for signatures.
   %%%_clamav = ClamAV signatures (both mains and daily).
   %%%_custom = Your custom signatures (if you've written any).
   %%%_mussel = phpMussel signatures included in your current signatures set
                which aren't from ClamAV.
   - Check against MD5 signatures when scanning? 0 = No, 1 = Yes [Default].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Check against general signatures when scanning? 0 = No, 1 = Yes [Default].
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
   - Check PE (Portable Executable) files (EXE, DLL, etc) against PE Sectional
     signatures when scanning? 0 = No, 1 = Yes [Default].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Check PE (Portable Executable) files (EXE, DLL, etc) against PE signatures
     when scanning? 0 = No, 1 = Yes [Default].
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
   - Check OLE objects against OLE signatures when scanning?
     0 = No, 1 = Yes [Default].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - Check filenames against filename based signatures when scanning?
     0 = No, 1 = Yes [Default].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Allow scanning with phpMussel_mail()? 0 = No, 1 = Yes [Default].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Enable file specific whitelist? 0 = No, 1 = Yes [Default].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - Check XML/XDP chunks against XML/XDP-chunk signatures when scanning?
     0 = No, 1 = Yes [Default].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - Check against Complex Extended signatures when scanning?
     0 = No, 1 = Yes [Default].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - Check against PDF signatures when scanning?
     0 = No, 1 = Yes [Default].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - Check against Shockwave signatures when scanning?
     0 = No, 1 = Yes [Default].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Signature matching length limiting options. Only change these if you
     know what you're doing. SD = Standard signatures. RX = PCRE (Perl
     Compatible Regular Expressions, or "Regex") signatures. FN = Filename
     signatures. If you notice php crashing when phpMussel attempts to scan,
     try lowering these "max" values. If possible and convenient, let me know
     when this happens and the results of whatever you try.
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
     crashes or similar problems. 0 = Disabled [Default], 1 = Enabled.
     "fail_silently"
 "files" (Categor�a)
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
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - If your system only allows specific types of files to be uploaded, or if
     your system explicitly denies certain types of files, specifying those
     filetypes in whitelists, blacklists and greylists can increase the speed
     at which scanning is performed by allowing the script to skip over certain
     filetypes. Format is CSV (comma separated values). If you want to scan
     everything, rather than whitelist, blacklist or greylist, leave the
     variable(/s) blank; Doing so will disable whitelist/blacklist/greylist.
     Logical order of processing is:
     - If the filetype is whitelisted, don't scan and don't block the file, and
       don't check the file against the blacklist or the greylist.
     - If the filetype is blacklisted, don't scan the file but block it anyway,
       and don't check the file against the greylist.
     - If the greylist is empty or if the greylist is not empty and the
       filetype is greylisted, scan the file as per normal and determine
       whether to block it based on the results of the scan, but if the
       greylist is not empty and the filetype is not greylisted, treat the file
       as blacklisted, therefore not scanning it but blocking it anyway.
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
 "attack_specific" (Categor�a)
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
     include()? 0 - No (do not check) [Default], 1 - Yes (check). Disable this
     option if you intend to upload any of the following to your system or CMS
     via your browser: php, JavaScript, HTML, python, perl files and etcetera.
     Enable this option if you do not have any additional protections on your
     system and do not intend to upload such files. If you use additional
     security in conjunction with phpMussel such as ZB Block, there is no need
     to turn this option on, because most of what phpMussel will look for (in
     the context of this option) are duplications of protections that are
     already provided.
   "block_control_characters"
   - Block any files containing any control characters (other than newlines)?
     ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) If you are -only- uploading plain-text,
     then you can turn this option on to provide some additional protection to
     your system. However, if you upload anything other than plain-text,
     turning this on may result in false positives.
     0 - Don't block [Default], 1 - Block.
   "corrupted_exe"
   - Corrupted files and parse errors. 0 = Ignore, 1 = Block [Default].
     Detect and block potentially corrupted PE (Portable Executable) files?
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
     filesize in KB. Default = 32768 (32MB). Zero or null value disables the
     threshold. Generally, this value shouldn't be less than the average
     filesize of file uploads that you want and expect to receive to your
     server or website, shouldn't be more than the filesize_limit directive,
     and shouldn't be more than roughly one fifth of the total allowable memory
     allocation granted to php via the php.ini configuration file. This
     directive exists to try to prevent phpMussel from using up too much memory
     (which would prevent it from being able to successfully scan files above a
     certain filesize).
 "compatibility" (Categor�a)
 - Compatibility directives for phpMussel.
    "ignore_upload_errors"
    - This directive should generally be disabled unless it is required for
      correct functionality of phpMussel on your specific system. Normally,
      when disabled, when phpMussel detects the presence of elements in the
      $_FILES array(), it will attempt to initiate a scan of the files that
      those elements represent, and, if those elements are blank or empty,
      phpMussel will return an error message. This is proper behaviour for
      phpMussel. However, for some CMS, empty elements in $_FILES can occur as
      a result of the natural behaviour of those CMS, or errors may be reported
      when there aren't any, in which case, the normal behaviour for phpMussel
      will be interfering with the normal behaviour of those CMS. If such a
      situation occurs for you, enabling this option will instruct phpMussel to
      not attempt to initiate scans for such empty elements, ignore them when
      found and to not return any related error messages, thus allowing
      continuation of the page request. 0 - OFF, 1 - ON.
    "only_allow_images"
    - If you only expect or only intend to allow images to be uploaded to your
      system or CMS, and if you absolutely do not require any files other than
      images to be uploaded to your system or CMS, this directive should be
      enabled, but should otherwise be disabled. If this directive is enabled,
      it will instruct phpMussel to indiscriminately block any uploads
      identified as non-image files, without scanning them. This may reduce
      processing time and memory usage for attempted uploads of non-image
      files. 0 - OFF, 1 - ON.

                                     ~ ~ ~


 7. FIRMA FORMATOS

 = FILENAME SIGNATURES =
   All filename signatures follow the format:
    NAME:FNRX
   Where NAME is the name to cite for that signature and FNRX is the regex
   pattern to match filenames (unencoded) against.

 = MD5 SIGNATURES =
   All MD5 signatures follow the format:
    HASH:FILESIZE:NAME
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size of
   that file and NAME is the name to cite for that signature.

 = ARCHIVE METADATA SIGNATURES =
   All archive metadata signatures follow the format:
    NAME:FILESIZE:CRC32
   Where NAME is the name to cite for that signature, FILESIZE is the total
   size (uncompressed) of a file contained within the archive and CRC32 is the
   crc32 checksum of that contained file.

 = PE SECTIONAL MD5 SIGNATURES =
   All PE Sectional MD5 signatures follow the format:
    FILESIZE:HASH:NAME
   Where HASH is the MD5 hash of a section of the PE file, FILESIZE is the
   total size of that file and NAME is the name to cite for that signature.

 = WHITELIST SIGNATURES =
   All Whitelist signatures follow the format:
    HASH:FILESIZE:TYPE
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size of
   that file and TYPE is the type of signatures the whitelisted file is to be
   immune against.

 = COMPLEX EXTENDED SIGNATURES =
   Complex Extended signatures are rather different to the other types of
   signatures possible with phpMussel, in that what they are matching against
   is specified by the signatures themselves and they can match against
   multiple criteria. The match criterias are delimited by ";" and the match
   type and match data of each match criteria is delimited by ":" as so that
   format for these signatures tends to look a bit like:
    $variable1:SOMEDATA;$variable2:SOMEDATA;SignatureName

 = EVERYTHING ELSE =
   All other signatures follow the format:
    NAME:HEX:FROM:TO
   Where NAME is the name to cite for that signature and HEX is a
   hexadecimal-encoded segment of the file intended to be matched by the given
   signature. FROM and TO are optional parameters, indicting from which and to
   which positions in the source data to check against (not supported by the
   mail function).

 = REGEX =
   Any form of regex understood and correctly processed by php should also be
   correctly understood and processed by phpMussel and its signatures. However,
   I'd suggest taking extreme caution when writing new regex based signatures,
   because, if you're not entirely sure what you're doing, there can be highly
   irregular and/or unexpected results. Take a look at the phpMussel
   source-code if you're not entirely sure about the context in which regex
   statements are parsed. Also, remember that all patterns (with exception to
   filename, archive metadata and MD5 patterns) must be hexadecimally encoded
   (foregoing pattern syntax, of course)!

 = WHERE TO PUT CUSTOM SIGNATURES? =
   Only put custom signatures in those files intended for custom signatures.
   Those files should contain "_custom" in their filenames. You should also
   avoid editing the default signature files, unless you know exactly what
   you're doing, because, aside from being good practise in general and aside
   from helping you distinguish between your own signatures and the default
   signatures included with phpMussel, it is good to stick to editing only the
   files intended for editing, because tampering with the default signature
   files can cause them to stop working correctly, due to the "maps" files: The
   maps files tell phpMussel where in the signature files to look for
   signatures required by phpMussel as per when required, and these maps can
   become out-of-sync with their associated signature files if those signature
   files are tampered with. You can put pretty much whatever you want into your
   custom signatures, so long as you follow the correct syntax. However, be
   careful to test new signatures for false-positives beforehand if you intend
   to share them or use them in a live environment.

 = SIGNATURE BREAKDOWN =
   The following is a breakdown of the types of signatures used by phpMussel:
   - "Normalised ASCII Signatures" (ascii_*). Checked against the contents of
      every non-whitelisted file targeted for scanning.
   - "Complex Extended Signatures" (coex_*). Mixed signature type matching.
   - "ELF Signatures" (elf_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to the ELF format.
   - "Portable Executable Signatures" (exe_*). Checked against the contents of
      every non-whitelisted targeted for scanning and matched to the PE format.
   - "Filename Signatures" (filenames_*). Checked against the filenames of
      files targeted for scanning.
   - "General Signatures" (general_*). Checked against the contents of every
      non-whitelisted file targeted for scanning.
   - "Graphics Signatures" (graphics_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to a known
      graphical file format.
   - "General Commands" (hex_general_commands.csv). Checked against the
      contents of every non-whitelisted file targeted for scanning.
   - "Normalised HTML Signatures" (html_*). Checked against the contents of
      every non-whitelisted HTML file targeted for scanning.
   - "Mach-O Signatures" (macho_*). Checked against the contents of every
      non-whitelisted file targeted for scanning and matched to the Mach-O
      format.
   - "Email Signatures" (mail_*). Checked against the $body variable parsed to
      the phpMussel_mail() function, which is intended to be the body of email
      messages or similar entities (potentially forum posts and etcetera).
   - "MD5 Signatures" (md5_*). Checked against the MD5 hash of the contents and
      the filesize of every non-whitelisted file targeted for scanning.
   - "Archive Metadata Signatures" (metadata_*). Checked against the CRC32 hash
      and filesize of the initial file contained inside of any non-whitelisted
      archive targeted for scanning.
   - "OLE Signatures" (ole_*). Checked against the contents of every
      non-whitelisted OLE object targeted for scanning.
   - "PDF Signatures" (pdf_*). Checked against the contents of every
      non-whitelisted PDF file targeted for scanning.
   - "Portable Executable Sectional Signatures" (pe_*). Checked against the MD5
      hash of each PE section and the filesize of every non-whitelisted file
      targeted for scanning and matched to the PE format.
   - "SWF Signatures" (swf_*). Checked against the contents of every
      non-whitelisted Shockwave file targeted for scanning.
   - "Whitelist Signatures" (whitelist_*). Checked against the MD5 hash of the
      contents and the filesize of every file targeted for scanning. Matched
      files will be immune to being matched by the type of signature mentioned
      in their whitelist entry.
   - "XML/XDP-Chunk Signatures" (xmlxdp_*). Checked against any XML/XDP chunks
      found within any non-whitelisted files targeted for scanning.
     (Note that any of these signatures may be easily disabled via
      phpmussel.ini).

                                     ~ ~ ~


 8. CONOCIDOS PROBLEMAS DE COMPATIBILIDAD

 PHP y PCRE
 - phpMussel requiere PHP y PCRE para ejecutar y funcionar correctamente. Sin
   PHP, o sin la PCRE extensi�n de PHP, phpMussel no ejecutar� o funcionar�
   correctamente. Debe asegurarse de que su sistema tiene tanto PHP y PCRE
   instalados y disponibles antes de descargar e instalar phpMussel.

 ANTI-VIRUS SOFTWARE COMPATIBILIDAD

 En su mayor parte, phpMussel debe ser bastante compatible con la mayor�a de
 anti-virus software. Aunque, conflictividades han sido reportados por un
 n�mero de usuarios en el pasado. Esta informaci�n de abajo es de
 VirusTotal.com, y describe un n�mero de falsos positivos reportados por
 diversos anti-virus programas contra phpMussel. Aunque esta informaci�n no es
 una garant�a absoluta de si o no se encontrar� con compatibilidad problemas
 entre phpMussel y su anti-virus software, se su anti-virus software se observa
 como marcar contra phpMussel, usted debe considerar desactivarlo antes de
 trabajar con phpMussel o deber�a considerar opciones alternativas a de su
 anti-virus software o phpMussel.

 Esta informaci�n ha sido actualizado 4 Febrero 2015 y es a hoy para todas las
 phpMussel versiones de la dos m�s recientes menores versiones (v0.5-v0.6) al
 momento de escribir esto.

 Ad-Aware                No hay conocidos problemas
 Agnitum                 No hay conocidos problemas
 AhnLab-V3               No hay conocidos problemas
 AntiVir                 No hay conocidos problemas
 Antiy-AVL               No hay conocidos problemas
 Avast                !  Informes "JS:ScriptSH-inf [Trj]"
 AVG                     No hay conocidos problemas
 Baidu-International     No hay conocidos problemas
 BitDefender             No hay conocidos problemas
 Bkav                    No hay conocidos problemas
 ByteHero                No hay conocidos problemas
 CAT-QuickHeal           No hay conocidos problemas
 ClamAV                  No hay conocidos problemas
 CMC                     No hay conocidos problemas
 Commtouch               No hay conocidos problemas
 Comodo                  No hay conocidos problemas
 DrWeb                   No hay conocidos problemas
 Emsisoft                No hay conocidos problemas
 ESET-NOD32              No hay conocidos problemas
 F-Prot                  No hay conocidos problemas
 F-Secure                No hay conocidos problemas
 Fortinet                No hay conocidos problemas
 GData                   No hay conocidos problemas
 Ikarus                  No hay conocidos problemas
 Jiangmin                No hay conocidos problemas
 K7AntiVirus             No hay conocidos problemas
 K7GW                    No hay conocidos problemas
 Kaspersky               No hay conocidos problemas
 Kingsoft                No hay conocidos problemas
 Malwarebytes            No hay conocidos problemas
 McAfee               !  Informes "New Script.c"
 McAfee-GW-Edition    !  Informes "New Script.c"
 Microsoft               No hay conocidos problemas
 MicroWorld-eScan        No hay conocidos problemas
 NANO-Antivirus          No hay conocidos problemas
 Norman               !  Informes "Kryptik.BQS"
 nProtect                No hay conocidos problemas
 Panda                   No hay conocidos problemas
 Qihoo-360               No hay conocidos problemas
 Rising                  No hay conocidos problemas
 Sophos                  No hay conocidos problemas
 SUPERAntiSpyware        No hay conocidos problemas
 Symantec             !  Informes "WS.Reputation.1"
 TheHacker               No hay conocidos problemas
 TotalDefense            No hay conocidos problemas
 TrendMicro              No hay conocidos problemas
 TrendMicro-HouseCall    No hay conocidos problemas
 VBA32                   No hay conocidos problemas
 VIPRE                   No hay conocidos problemas
 ViRobot                 No hay conocidos problemas


                                     ~ ~ ~


�ltima Actualizaci�n: 4 Febrero 2015 (2015.02.04).
EOF
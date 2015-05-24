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

 PHPMUSSEL COPYRIGHT 2013 y m�s all� GNU/GPL V.2 por Caleb M (Maikuolan).

 Este script es gratis software; puede redistribuirlo y/o modificarlo seg�n los
 t�rminos de la GNU General P�blica Licencia como publicada por la Free
 Software Foundation; versi�n 2 de la licencia, o cualquier posterior versi�n.
 Este script se distribuye con la esperanza de que ser� �til, pero SIN NINGUNA
 GARANT�A; tambi�n, sin ninguna impl�cita garant�a de COMERCIALIZACI�N o
 IDONEIDAD PARA UN PARTICULAR PROP�SITO. Vea la GNU General P�blica Licencia
 para m�s detalles, ubicado en el "LICENCE" archivo dentro del "_docs"
 directorio del asociado paquete y repositorio para este archivo y disponible
 tambi�n de: <http://www.gnu.org/licenses/> <http://opensource.org/licenses/>.

 Un especial agradecimiento a ClamAV para la inspiraci�n del proyecto y para
 las firmas que este script utiliza, sin la cual, la script probablemente no
 existir�a, o en el mejor de, tendr�a un muy limitado valor
 <http://www.clamav.net/>.

 Un especial agradecimiento a Sourceforge y GitHub para alojar los archivos de
 proyecto, situado en <http://phpmussel.sourceforge.net/> y
 <https://github.com/Maikuolan/phpMussel/>, a Spambot Security para la
 phpMussel discusi�n foros, situado en
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, y a las adicionales
 fuentes de un n�mero de las firmas utilizadas por phpMussel: SecuriteInfo.com
 <http://www.securiteinfo.com/>, PhishTank <http://www.phishtank.com/>,
 NLNetLabs <http://nlnetlabs.nl/> y otros, y agradecimiento especial a todos
 aquellos que apoyan el proyecto, a cualquier otra persona que yo haya olvidado
 de lo contrario mencionar, y a usted, por el uso de la script.

 Este documento y asociado paquete pueden descargar de gratis desde:
 - Sourceforge <http://phpmussel.sourceforge.net/>.
 - GitHub <https://github.com/Maikuolan/phpMussel/>.

                                     ~ ~ ~


 2A. C�MO INSTALAR (PARA NAVEGADORES)

 Espero para agilizar este proceso al hacer un instalador en alg�n momento en
 un futuro no muy lejano, pero hasta entonces, siga estas instrucciones para ha
 phpMussel functione en *mayor�a de sistemas y CMS:

 1) Con tu leyendo esto, estoy asumiendo que usted ha descargado una copia de
    la script, descomprimido y tenerlo en alg�n lugar en su computer. Desde
    aqu�, usted querr� averiguar d�nde en el host o CMS que desea para colocar
    el contenido. Un directorio como /public_html/phpmussel/ o similar (aunque,
    no importa que usted elija, a condici�n de que se algo que est�s satisfecho
    con) ser� suficiente. Antes usted enviar archivos a su host, seguir
    leyendo..

 2) Abrir "phpmussel.php", busque la l�nea que comienza con "$vault=", y
    reemplazar la cadena entre las siguientes comillas en esa l�nea con la
    exacta verdadera ubicaci�n del "vault" directorio de phpMussel. Usted ver�
    tal un directorio en el compactado archivo que ha descargado (asumiendo que
    no desea revolver todo la script, mantener la misma estructura de archivos
    y directorios como lo fue el original). Este "vault" directorio normalmente
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
    puede dejar solos, pero CHMOD estado debe ser comprobado si ha tenido
    problemas de permisos en el pasado en su sistema (predefinido, deber�a ser
    algo como "755").

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

 1) Con tu leyendo esto, estoy asumiendo que usted ha descargado una copia de
    la script, descomprimido y tenerlo en alg�n lugar en su computer. Cuando se
    ha determinado que usted es feliz con el lugar elegido para phpMussel,
    continuar.

 2) phpMussel requiere php para ser instalado en la host m�quina para ejecutar.
    Si usted no has php instalado en su m�quina, por favor, instalar php en su
    m�quina, siguiendo las instrucciones suministradas por el php instalador.

 2) Abrir "phpmussel.php", busque la l�nea que comienza con "$vault=", y
    reemplazar la cadena entre las siguientes comillas en esa l�nea con la
    exacta verdadera ubicaci�n del "vault" directorio de phpMussel. Usted ver�
    tal un directorio en el compactado archivo que ha descargado (asumiendo que
    no desea revolver todo la script, mantener la misma estructura de archivos
    y directorios como lo fue el original). Este "vault" directorio normalmente
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
 o compactados archivos usted especifique impl�citamente. Para ello,
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
    > Comprobando '/user_name/public_html/my_file.html':
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
   Par�metros opcionales: (nada)
   Ejemplo: ?pword=[script_password]&phpmussel=update
   ~
   Qu� hace: Comprobar por actualizaciones para ambos phpMussel y sus firmas.
             Si las actualizaciones comprobar tienen �xito y actualizaciones
             est� encuentran, intentar� descargar e instalar estas
             actualizaciones. Si las actualizaciones comprobar fallan,
             actualizaciones comprobar abortar�. Los resultados de todo el
             proceso se imprimen en la pantalla. Recomiendo comprobar al menos
             una vez por mes para asegurar que sus firmas y su copia de
             phpMussel se mantienen actualizada (a menos que, naturalmente,
             usted est� comprobando las actualizaciones e instalandolos
             manualmente, que, aun as� sigo recomendando hacer al menos uno por
             mes). Comprobar m�s de dos veces por mes es probablemente in�til,
             en consideraci�n que (en el momento de escribir este) estoy
             trabajando en este proyecto solo y estoy muy improbable de ser
             capaz de producir actualizaciones de cualquier tipo con m�s
             frecuencia que la (ni tengo particular quiero para hacerlo en la
             mayor parte).
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
 en la copia de este script cuando descargado, todos los archivos que pueden
 ser potencialmente creados como resultado de su uso de este script, junto con
 una breve descripci�n de lo que todos estos archivos son para.

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
    diferentes versiones (no se requiere para lo adecuado funcionalidad de la
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
    adecuado funcionalidad de la script).
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
 /_testfiles/swf_standard_testfile.swf (Prueba archivo, Incluido)
    Prueba archivo para probando phpMussel SWF firmas.
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
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/coex_clamav.cvd (Firmas, Incluidos)
 /vault/coex_custom.cvd (Firmas, Incluidos)
 /vault/coex_mussel.cvd (Firmas, Incluidos)
    Archivos para Complejo Extendido firmas.
    Requerido si la opci�n de Complejo Extendido firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    puede eliminarlo si la opci�n est� desactivada.
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
    puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/filenames_clamav.cvd (Firmas, Incluidos)
 /vault/filenames_custom.cvd (Firmas, Incluidos)
 /vault/filenames_mussel.cvd (Firmas, Incluidos)
    Archivos para archivo nombre firmas.
    Requerido si la opci�n de filename firmas en phpmussel.ini est� habilitado.
    Se puede eliminarlo si la opci�n est� desactivada.
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
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    Se puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/greylist.csv (Firmas, Incluidos/Creados)
    CSV de las firmas en la Greylist indicando para phpMussel las firmas que
    deben ser ignorados (archivo ser� recreado autom�ticamente si eliminado).
    ~
 /vault/hex_general_commands.csv (Firmas, Incluidos)
    Hex-codificado CSV de generales comandos detecciones opcionalmente
    utilizado por phpMussel. Requerido si la opci�n de generales comandos
    detecciones en phpmussel.ini est� habilitado. Se puede eliminarlo si la
    opci�n est� desactivada.
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
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    Se puede eliminarlo si la opci�n est� desactivada.
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
    Se puede eliminarlo si no se utilizado.
    ~
 /vault/md5_clamav.cvd (Firmas, Incluidos)
 /vault/md5_custom.cvd (Firmas, Incluidos)
 /vault/md5_mussel.cvd (Firmas, Incluidos)
    Archivos para MD5 basadas firmas.
    Requerido si la opci�n de MD5 basadas firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/metadata_clamav.cvd (Firmas, Incluidos)
 /vault/metadata_custom.cvd (Firmas, Incluidos)
 /vault/metadata_mussel.cvd (Firmas, Incluidos)
    Archivos para archivo metadatos firmas.
    Requerido si la opci�n de archivo metadatos firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    puede eliminarlo si la opci�n est� desactivada.
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
    puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/pe_clamav.cvd (Firmas, Incluidos)
 /vault/pe_custom.cvd (Firmas, Incluidos)
 /vault/pe_mussel.cvd (Firmas, Incluidos)
    Archivos para PE Secci�nal firmas.
    Requerido si la opci�n de PE Secci�nal firmas en phpmussel.ini est�
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
    ~
 /vault/switch.dat (Other, Included)
    Esto controla y establece ciertas variables.
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
    whitelist.
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
    habilitado. Se puede eliminarlo si la opci�n est� desactivada.
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
    - Habilitando esta directiva instruir� la script para intentar para
      eliminar inmediatamente cualquier escaneado intentado archivo cargas
      ajustando a los criterios de detecci�n, si trav�s de firmas o de otras
      maneras. Archivos determinados como limpia no ser�n tocados. En el caso
      de los compactados archivos, la totalidad del compactado archivo ser�
      eliminado (independientemente de si el archivo infractor es s�lo uno de
      varios archivos contenida dentro del compactado archivo). Para el caso de
      archivo carga escaneo, en general, no es necesario activar esta opci�n,
      porque en general, php purgar� autom�ticamente el contenido de su cach�
      cuando la ejecuci�n ha terminado, lo que significa que lo en general va
      eliminar cualquier archivos cargados a trav�s de �l con el servidor a no
      ser que se han movido, copiado o eliminado ya. La opci�n se a�ade aqu�
      como una medida adicional de seguridad para el adicional paranoide y para
      aquellos cuyas copias de php no siempre se comportan de la manera
      prevista.
      0 - Despu�s escaneando, dejar el archivo solo [Predefinido],
      1 - Despu�s escaneando, si no se limpia, eliminar inmediatamente.
    "lang"
    - Especifique el idioma predefinido para phpMussel.
    "quarantine_key"
    - phpMussel es capaz de poner en cuarentena intentado archivo cargas en
      aisladamente dentro de la phpMussel vault, si esto es algo que usted
      quiere que haga. Usuarios casual de phpMussel de los cuales simplemente
      desean proteger sus website o hosting ambiente sin tener ning�n inter�s
      con analizando profundamente cualquier marcados intentados archivos
      cargas deber�a dejar esta funcionalidad deshabilitado, pero cualquier
      usuarios interesados en m�s an�lisis de marcados intentados archivos
      cargas para la investigaci�n de malware o para cosas similares debe
      habilitar esta funcionalidad. Cuarentenando de marcados intentados
      archivos cargas a veces puede tambi�n ayudar en la depuraci�n de falsos
      positivos, si esto es algo que ocurre con frecuencia para usted. Para
      deshabilitar la funcionalidad de cuarentena, simplemente dejar la
      directiva "quarantine_key" vac�o, o borrar el contenidos de que directiva
      si no est� ya vac�o. Para habilitar la funcionalidad de cuarentena,
      entrar alg�n valor en la directiva. La "quarantine_key" es un importante
      caracter�stica de seguridad de la funcionalidad de cuarentena requiere
      como un medio para la prevenci�n de la explotaci�n de la funcionalidad de
      cuarentena por potenciales atacantes y como un medio de evitar cualquier
      potencial ejecuci�n de los datos almacenados dentro la cuarentena. La
      "quarantine_key" deber�a ser tratado de la misma manera que sus
      contrase�as: El m�s grande es el mejor, y gu�rdela bien. Para un mejor
      efecto, utilice conjuntamente con "delete_on_sight".
    "quarantine_max_filesize"
    - El m�ximo archivo tama�o permitido para archivos para ser cuarentenada.
      Archivos que superen el valor especificado aqu� NO ser�n cuarentenada.
      Esta directiva es importante como un medio de hacer que sea m�s dif�cil
      para cualquier potenciales atacantes a inundar su cuarentena con datos no
      deseados que puede causar el excesivo uso de datos en su hosting
      servicio. Valor es en KB.
      Predefinido =2048 =2048KB =2MB.
    "quarantine_max_usage"
    - El m�xima uso de memoria permitida para la cuarentena. Si la total
      memoria utilizada por la cuarentena alcanza este valor, los m�s antiguos
      cuarentenado archivos ser�n eliminado hasta que la total memoria
      utilizada ya no alcanza este valor. Esta directiva es importante como un
      medio de hacer que sea m�s dif�cil para cualquier potenciales atacantes a
      inundar su cuarentena con datos no deseados que puede causar el excesivo
      uso de datos en su hosting servicio. Valor es en KB.
      Predefinido =2048 =2048KB =2MB.
    "honeypot_mode"
    - Cuando la honeypot modo est� habilitado, phpMussel intentar� cuarentenar
      cada archivo carga que encuentra, independientemente de si o no el
      archivo que se est� cargado coincide con las firmas inclu�das, y no real
      escanear o an�lisis de esos intentados archivos cargas van a ocurrir.
      Esta funcionalidad debe ser �til para aquellos que deseen utilizar
      phpMussel a los efectos del virus/malware investigaci�n, pero no se
      recomendado habilitar esta funcionalidad si el uso de phpMussel por el
      usuario es para real archivo carga escaneando ni recomendado usar la
      honeypot funcionalidad para fines otro que de la honeypot. Por
      predefinido, esta opci�n est� desactivada.
      0 = Deshabilitado [Predefinido], 1 = Habilitado.
 "signatures" (Categor�a)
 - Configuraci�n de firmas.
   %%%_clamav = ClamAV firmas (ambos mains y daily).
   %%%_custom = Sus personalizadas firmas (si usted ha escritos algunas).
   %%%_mussel = phpMussel firmas incluidos en su corriente firmas conjunto que
                no son de ClamAV.
   - Cotejar contra MD5 firmas cuando escaneando? 0 = No, 1 = S� [Predefinido].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Cotejar contra gen�ricas firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Cotejar contra normalizados ASCII firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - Cotejar contra normalizados HTML firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - Cotejar PE (Port�til Ejecutable) archivos (EXE, DLL, etc) con PE Secci�nal
     firmas cuando escaneando? 0 = No, 1 = S� [Predefinido].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Cotejar PE (Port�til Ejecutable) archivos (EXE, DLL, etc) con PE firmas
     cuando escaneando? 0 = No, 1 = S� [Predefinido].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Cotejar ELF archivos con ELF firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Cotejar Mach-O archivos (OSX, etc) con Mach-O firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Cotejar gr�ficos archivos con firmas basado en gr�ficos cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Cotejar contenidos de compactados archivos con compactados archivos
     metadatos firmas cuando escaneando? 0 = No, 1 = S� [Predefinido].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Cotejar OLE objetos con OLE firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - Cotejar nombres de archivos con firmas basado en nombres cuando
     escaneando? 0 = No, 1 = S� [Predefinido].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Permitir escaneando con phpMussel_mail()? 0 = No, 1 = S� [Predefinido].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Habilitar archivo espec�fica whitelist? 0 = No, 1 = S� [Predefinido].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - Cotejar XML/XDP trozos con XML/XDP-Chunk firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - Cotejar contra Complejo Extendido firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - Cotejar contra PDF firmas cuando escaneando? 0 = No, 1 = S� [Predefinido].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - Cotejar contra Shockwave firmas cuando escaneando?
     0 = No, 1 = S� [Predefinido].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Firma cotejando longitud limitando opciones. S�lo cambiarlos si sabes lo
     que est�s haciendo. SD = Est�ndar firmas. RX = PCRE (Perl Compatibles
     Regulares Expresiones, o "Regex") firmas. FN = Firmas basados en nombre de
     archivos. Si usted notar php estrellarse cuando phpMussel intentar
     escanear, intente reducir estos "max" valores. Si es posible y
     conveniente, av�same cuando esto ocurre y los resultados de lo que
     intentan.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Debe phpMussel informan cuando los firmas archivos est�n desaparecidos o
     da�ados? Si fail_silently est� deshabilitado, desaparecidos y da�ados
     archivos ser� reportado cuando escaneando, y si fail_silently est�
     habilitado, desaparecidos y da�ados archivos ser� ignorado, con escaneando
     reportado para lo archivos que no hay cualquier problemas. Esto
     generalmente debe ser dejar sola a menos que usted est� experimentando
     estrellarse o problemas similares.
     0 = Deshabilitado, 1 = Habilitado [Predefinido].
     "fail_silently"
 "files" (Categor�a)
 - General configuraci�n para el manejo de archivos.
   "max_uploads"
   - M�ximo permitido n�mero de archivos para escanear durante archivo carga
     escaneo antes de abortando la escaneo e informando al usuario est�n
     cargando demasiado simult�neamente! Proporciona protecci�n contra un
     te�rico ataque por lo cual un atacante intenta DDoS su sistema o CMS por
     sobrecargando phpMussel para ralentizar el proceso de php a niveles
     inoperables. Recomendado: 10. Es posible que desee aumentar o reducir este
     n�mero dependiendo de la velocidad de su hardware. Notar que este n�mero
     no tiene en cuenta o incluir el contenidos de compactados archivos.
   "filesize_limit"
   - L�mite del tama�o de archivos en KB. 65536 = 64MB [Predefinido], 0 = Sin
     l�mite (siempre en la greylist), cualquier (positivo) num�rico valor
     aceptado. Esto puede ser �til cuando su php configuraci�n limita la
     cantidad de memoria un proceso puede contener o si su php configuraci�n
     limita el tama�o de archivo cargas.
   "filesize_response"
   - Qu� hacer con los archivos que superen el l�mite del tama�o de archivos
     (si existe). 0 - Whitelist, 1 - Blacklist [Predefinido].
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - Si su sistema s�lo permite ciertos tipos de archivos para ser cargado, o
     si su sistema niega expl�citamente ciertos tipos de archivos,
     especificando los tipos de archivos en la whitelist, blacklist y/o
     greylist puede aumentar la velocidad a que escaneando se realizado por
     permitiendo la script para saltar sobre ciertos tipos de archivos. Formato
     es CSV (comas separados valores). Si desea escanear todo, en lugar de
     utilizando la whitelist, blacklist o greylist, dejar las variables en
     blanco; haciendo tal desactivar� la whitelist/blacklist/greylist.
     L�gico orden de procesamiento es:
     - Si el tipo de archivo est� en la whitelist, no escanear y no bloquear el
       archivo, y no cotejar el archivo con la blacklist o la greylist.
     - Si el tipo de archivo est� en la blacklist, no escanear el archivo, pero
       bloquearlo en todo caso, y no cotejar el archivo con la greylist.
     - Si la greylist est� vac�a o si la greylist est� no vac�a y el tipo de
       archivo est� en la greylist, escanearlo como normal y determinar si para
       bloquearlo basado en los resultados de la escaneo, pero si la greylist
       est� no vac�a y el tipo de archivo est� no en la greylist, tratar el
       archivo como si est� en la blacklist, por lo tanto no escanearlo pero
       bloquearlo en todo caso.
   "check_archives"
   - Intente comprobar el contenido de los compactados archivos?
     0 - No (no comprobar), 1 - S� (comprobar) [Predefinido].
     * Corrientemente, s�lo la comprobaci�n de BZ, GZ, LZF y ZIP archivos est�
       soportado (comprobaci�n de RAR, CAB, 7z y etc�tera no soportado en este
       momento).
     * Esto no es infalible! Mientras yo altamente recomiendo mantener este
       habilitado, no puedo garantizar que siempre encontrar� todo.
     * Tambi�n ser conscientes que la comprobaci�n de compactados archivos
       corrientemente no es recursivo para ZIPs.
   "filesize_archives"
   - Heredar tama�o de archivos blacklist/whitelist para los contenidos de
     compactados archivos? 0 - No (todo en la greylist), 1 - S� [Predefinido].
   "filetype_archives"
   - Heredar tipos de archivos blacklist/whitelist para los contenidos de
     compactados archivos? 0 - No (todo en la greylist), 1 - S� [Predefinido].
   "max_recursion"
   - M�ximo recursividad nivel l�mite para compactados archivos.
     Predefinido = 10.
 "attack_specific" (Categor�a)
 - Configuraci�n para ataque espec�ficas detecciones (no basado en CVDs).
   * Camale�n ataque detecci�n: 0 = Deshabilitado, 1 = Habilitado.
   "chameleon_from_php"
   - Buscar para php c�digo en archivos que no est�n php archivos ni
     reconocidos compactados archivos.
   "chameleon_from_exe"
   - Buscar para PE m�gico n�mero en archivos que no est�n ejecutables ni
     reconocidos compactados archivos y para ejecutables cuyo m�gicos n�meros
     son incorrectas.
   "chameleon_to_archive"
   - Buscar para compactados archivos cuyo m�gicos n�meros son incorrectas
     (Soportado: BZ, GZ, RAR, ZIP, RAR, GZ).
   "chameleon_to_doc"
   - Buscar para office documentos cuyo m�gicos n�meros son incorrectas
     (Soportado: DOC, DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Buscar para im�genes cuyo m�gicos n�meros son incorrectas (Soportado: BMP,
     DIB, PNG, GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Buscar para PDF archivos cuyo m�gicos n�meros son incorrectas.
   "archive_file_extensions" y "archive_file_extensions_wc"
   - Reconocido compactado archivo extensiones (formato es CSV; s�lo debe
     agregar o eliminar cuando problemas ocurrir; eliminando innecesariamente
     puede causar falsos positivos a aparecer para compactados archivos,
     mientras a�adiendo innecesariamente har� esencialmente whitelist que
     cuales eres a�adiendo desde ataque espec�fica detecci�n; modificar con
     precauci�n; Tambi�n notar que esto no tiene efecto en aquellos compactados
     archivos que pueden y no pueden ser analizado a contenido nivel). La
     lista, como es a predefinici�n, describe los formatos m�s com�nmente
     utilizados a trav�s de la mayor�a de sistemas y CMS, pero intencionalmente
     no es necesariamente exhaustiva.
   "general_commands"
   - Buscar contenidos de archivos para generales comandos como tal eval(),
     exec() y include()? 0 - No (no buscar) [Default], 1 - S� (buscar).
     Deshabilitar esta opci�n si tiene intenci�n de cargando cualquiera de los
     siguientes para su sistema o CMS a trav�s de su navegador: php,
     JavaScript, HTML, python, perl archivos y etc�tera. Habilitar esta opci�n
     si usted no tiene cualquier adicional protecci�n en su sistema y no tiene
     intenci�n de cargando estos tipos de archivos. Si utiliza adicional
     seguridad junto con phpMussel como tal ZB Block, no hay necesidad de
     habilitar esta opci�n, porque la mayor parte de lo que phpMussel buscar�
     (en el contexto de esta opci�n) son duplicaciones de protecciones que ya
     previsto.
   "block_control_characters"
   - Bloquear cualquier archivos que contenga cualquier control car�cter
     (aparte de saltos de l�nea)? ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) Si usted
     s�lo cargar texto sin cualquier formato, usted puede habilitar esta opci�n
     para proporcionar alguna adicional protecci�n para su sistema. Pero, si
     usted cargar cualquier cosa otro de texto sin cualquier formato,
     habilitando esto puede dar lugar a falsos positivos.
     0 - No bloquear [Predefinido], 1 - Bloquear.
   "corrupted_exe"
   - Corrompido archivos y procesamiento errores.
     0 = Ignorar, 1 = Bloquear [Predefinido].
     Detectar y bloquear potencialmente corrompido PE (Port�til Ejecutable)
     archivos? Frecuentemente (pero no siempre), cuando ciertos aspectos de un
     PE archivo est�n corrompido, da�ados o no podr� ser analizado
     correctamente, lo puede ser indicativo de una infecci�n viral. Los
     procesos utilizados por la mayor�a de los antivirus programas para
     detectar un virus en PE archivos requerir analizando esos archivos en
     ciertas maneras, que, si el programador de un virus es consciente de,
     intentar� espec�ficamente para prevenir, con el fin de permitir su virus
     permanezca sin ser detectado.
   "decode_threshold"
   - Opcional limitaci�n a la longitud de puros datos a que dentro de
     decodificaci�n comandos deben ser detectados (en caso de que los hay
     notable rendimiento problemas mientras que escaneando). Valor es un entero
     n�mero representando el tama�o de archivos en KB.
     Predefinido = 512 (512KB). Cero o nulo valor deshabilita la limitaci�n
     (eliminando cualquier tal limitaci�n basado sobre la tama�o de archivos).
   "scannable_threshold"
   - Opcional limitaci�n a la longitud de puros datos para que phpMussel se
     permitido leer y escanear (en caso de que los hay notable rendimiento
     problemas mientras que escaneando). Valor es un entero n�mero
     representando el tama�o de archivos en KB. Predefinido = 32768 (32MB).
     Cero o nulo valor deshabilita la limitaci�n. En general, Este valor no
     debe ser inferior a la media tama�o de archivo cargas que desea y espera
     recibir a su servidor o website, no debe ser mayor que el filesize_limit
     directiva, y no debe ser m�s de aproximadamente una quinta parte de la
     total permisible memoria asignaci�n concedida a php a trav�s de la php.ini
     configuraci�n archivo. Esta directiva existe para intratar prevenir
     phpMussel del uso de demasiada memoria (eso ser�a prevenir que sea capaz
     para escanear archivos con �xito encima de un cierto tama�o de archivos).
 "compatibility" (Categor�a)
 - Compatibilidad directivas para phpMussel.
   "ignore_upload_errors"
   - Esta directiva, en general, debe ser deshabilitado, a menos que se
     requiere para la correcta funcionalidad de phpMussel en su espec�fico
     sistema. Normalmente, cuando est� desactivado, cuando phpMussel detecta
     la presencia de elementos en la $_FILES array(), intentar� iniciar un
     escaneo de los archivos que esos elementos representan, y, si esos
     elementos est�n blanco o vac�o, phpMussel devolver� un mensaje de error.
     Este es el comportamiento natural para phpMussel. Pero, para algunos CMS,
     vac�os elementos en $_FILES puede ocurrir como resultado del
     comportamiento natural de los CMS, o errores pueden ser reportados cuando
     no existe ninguna, en cuyo caso, el comportamiento natural para phpMussel
     ser� interfiriendo con el comportamiento natural de los CMS. Si tal
     situaci�n ocurre para usted, habilitando esta opci�n instruir� phpMussel
     no intentar iniciar un escaneo para tales vac�os elementos, ignorarlos
     cuando encontrado y no devuelva cualquier relacionado mensaje de error,
     as� permitiendo la continuaci�n de la p�gina cargando.
     0 - DESHABILITADO, 1 - HABILITADO.
   "only_allow_images"
   - Si s�lo esperas o s�lo quieren permitir im�genes para ser cargado a su
     sistema o CMS, y si usted absolutamente no requiere cualquieres archivos
     otro que im�genes para ser cargado a su sistema o CMS, esta directiva debe
     ser habilitado, pero por lo dem�s debe ser deshabilitado. Si esta
     directiva est� habilitada, instruir� phpMussel para indiscriminadamente
     bloquear cualquieres cargas identificado como archivos que no son imagen,
     sin escaneandolos. Esto puede reducir el tiempo de procesamiento y el uso
     de memoria para intentado cargas de archivos que no son imagen.
     0 - DESHABILITADO, 1 - HABILITADO.
 "heuristic" (Categor�a)
 - Heur�sticas directivas para phpMussel.
   "threshold"
   - Hay ciertas firmas de phpMussel eso tienen la intenci�n de identificar
     sospechosas y potencialmente maliciosos cualidades de los archivos que se
     cargan sin que en ellos la identificaci�n de los archivos que se cargan
     espec�ficamente como malicioso. Este "threshold" (umbral) valor dice
     phpMussel qu� lo m�ximo total peso de sospechosas y potencialmente
     maliciosos cualidades de los archivos que se cargan eso es permisible es
     antes de que esos archivos han de ser se�alado como malicioso. La
     definici�n de peso en este contexto es el n�mero total de sospechosas y
     potencialmente maliciosos cualidades identificados. Por predefinido, este
     valor es 3. Un valor inferior generalmente resultar� en una mayor
     incidencia de falsos positivos pero un mayor n�mero de archivos maliciosos
     siendo identificado, mientras un valor mayor generalmente resultar� en una
     inferior incidencia de falsos positivos pero un inferior n�mero de
     archivos maliciosos siendo identificado. Generalmente es mejor dejar este
     valor en su predefinido a menos que usted est� experimentando problemas
     relacionados con ella.

                                     ~ ~ ~


 7. FIRMA FORMATOS

 = FIRMAS BASADAS EN LAS NOMBRES DEL ARCHIVOS =
   Todas firmas basadas en las nombres del archivos seguir el formato:
    NOMBRE:FNRX
   Donde NOMBRE es el nombre a citar para esa firma y FNRX es la regular
   expresi�n para cotejar nombres de archivos (sin codificar) con.

 = MD5 FIRMAS =
   Todos MD5 firmas seguir el formato:
    HASH:TAMA�O:NOMBRE
   Donde HASH es el MD5 hash de un entero archivo, TAMA�O es el total tama�o
   de eso archivo y NOMBRE es el nombre a citar para esa firma.

 = COMPACTADOS ARCHIVOS METADATOS FIRMAS =
   Donde compactados archivos metadatos firmas seguir el formato:
    NOMBRE:TAMA�O:CRC32
   Donde NOMBRE es el nombre a citar para esa firma, TAMA�O es el total tama�o
   (sin comprimir) de un archivo contenido dentro el compactado archivo y CRC32
   es el crc32 suma de comprobaci�n de eso contenido archivo.

 = PE SECCI�NAL FIRMAS =
   Todos PE Secci�nal firmas seguir el formato:
    TAMA�O:HASH:NOMBRE
   Donde HASH es el MD5 hash de una secci�n del PE archivo, TAMA�O es el total
   tama�o de esa secci�n y NOMBRE es el nombre a citar para esa firma.

 = WHITELIST FIRMAS =
   Todos Whitelist firmas seguir el formato:
    HASH:TAMA�O:TIPO
   Donde HASH es el MD5 hash de un entero archivo, TAMA�O es el total tama�o de
   eso archivo y TIPO es el tipo of firmas el archivo en la whitelist es estar
   inmune contra.

 = COMPLEJO EXTENDIDO FIRMAS =
   Complejo Extendido firmas son bastante diferentes a los otros tipos de
   firmas posibles con phpMussel, en que qu� ellos son cotejando contra se
   especificado por las firmas ellos mismos y que ellos pueden cotejar contra
   m�ltiples criterios. La cotejar criterios est�n delimitados por ";" y la
   cotejar tipo y cotejar datos de cada cotejar criterio es delimitado por ":"
   como tal que formato para estas firmas tiene tendencia a aparecer como:
    $variable1:SOMEDATA;$variable2:SOMEDATA;FirmaNombre

 = TODO LO DEM�S =
   Todas las dem�s firmas seguir el formato:
    NOMBRE:HEX:DESDE:PARA
   Donde NOMBRE es el nombre a citar para esa firma y HEX es un hexadecimal
   codificado segmento del archivo propuesto para ser comprobado por la firma
   dado. DESDE y PARA son opcionales par�metros, indicando desde cual y para
   cual posiciones en los datos de origen a cotejar contra (no soportado por
   la mail funci�n).

 = REGEX =
   Cualquier forma de regex entendido y correctamente procesado por php tambi�n
   debe entenderse y procesado correctamente por phpMussel y sus firmas. Pero,
   yo sugerir�a tomar mucho cuidado cuando escribiendo nuevas firmas basado en
   regex, porque, si no est�s del todo seguro de lo que est�s haciendo, puede
   haber altamente irregulares e/o inesperados resultados. Mirar el c�digo
   fuente para phpMussel si no est�s del todo seguro sobre el contexto para lo
   cual las regex declaraciones son procesado. Tambi�n, recordar que todos los
   patrones (con excepci�n para nombre de archivo, compactado archivo metadato
   y MD5 patrones) debe ser hexadecimal codificado (con excepci�n de la patr�n
   sintaxis)!

 = DONDE PONER PERSONALIZADAS FIRMAS? =
   S�lo poner personalizadas firmas en esos archivos destinados para
   personalizadas firmas. Estos archivos deben contener "_custom" en sus
   nombres. Tambi�n debe evitar editando de los predefinidos firmas archivos
   que no son nombrado como tal, a menos que sepa exactamente lo que est�
   haciendo, porque, adem�s de ser una buena pr�ctica en general y adem�s de
   desde ayudando distinguir entre sus propias firmas y la predefinido firmas
   incluido con phpMussel, que es bueno para mantener para editando s�lo los
   archivos destinados para editando, porque la manipulaci�n de los
   predefinidos firmas archivos puede causarlos cesar funcionando
   correctamente, por raz�n del "maps" archivos: Los "maps" archivos instruir
   phpMussel donde en los firmas archivos para mirar por firmas requeridas por
   phpMussel como por cuando requerido, y estos mapas pueden convertirse fuera
   de sincronizaci�n con sus asociados firmas archivos si esos firmas archivos
   est�n manipulados. Usted puede poner m�s o menos lo que quieras en sus
   personalizadas firmas, siempre y cuando usted sigue la sintaxis correcta.
   Pero, tener cuidado para probar nuevas firmas para falsos positivos de
   antemano si tiene intenci�n de compartirlas o utilizarlos en un real
   entorno.

 = FIRMA DESGLOSE =
   El siguiente es el desglose de los tipos de firmas utilizado por phpMussel:
   - "Normalizados ASCII Firmas" (ascii_*). Cotejado contra los contenidos de
      cada archivo que no est� en la whitelist que es destinado para
      escaneando.
   - "Complejo Extendido Firmas" (coex_*). Mixtas tipos de firmas para
      cotejar/comprobar.
   - "ELF Firmas" (elf_*). Cotejado contra los contenidos de cada archivo que
      no est� en la whitelist que es destinado para escaneando y verificado
      como del ELF formato.
   - "Port�til Ejecutable Firmas" (exe_*). Cotejado contra los contenidos de
      cada archivo que no est� en la whitelist que es destinado para escaneando
      y verificado como del PE formato.
   - "Firmas Basadas En Las Nombres Del Archivos" (filenames_*). Cotejado
      contra los nombres de archivos destinado para escaneando.
   - "Generales Firmas" (general_*). Cotejado contra los contenidos de cada
      archivo que no est� en la whitelist que es destinado para escaneando.
   - "Gr�ficas Firmas" (graphics_*). Cotejado contra los contenidos de cada
      archivo que no est� en la whitelist que es destinado para escaneando y
      verificado como de un conocido gr�ficos formato.
   - "Generales Comandos" (hex_general_commands.csv). Cotejado contra los
      contenidos de cada archivo que no est� en la whitelist que es destinado
      para escaneando.
   - "Normalizados HTML Firmas" (html_*). Cotejado contra los contenidos de
      cada archivo que no est� en la whitelist que es destinado para escaneando
      y verificado como del HTML formato.
   - "Mach-O Firmas" (macho_*). Cotejado contra los contenidos de cada archivo
      que no est� en la whitelist que es destinado para escaneando y verificado
      como del Mach-O formato.
   - "Email Firmas" (mail_*). Cotejado contra la $body variable procesada por
      la phpMussel_mail() funci�n, which is intended to be the body of email
      messages or similar entities (potentially forum posts and etcetera).
   - "MD5 Firmas" (md5_*). Cotejado contra el MD5 hash de los contenidos y el
      tama�o de cada archivo que no est� en la whitelist que es destinado para
      escaneando.
   - "Compactados Archivos Metadatos Firmas" (metadata_*). Cotejado contra el
      CRC32 hash y tama�o del inicial archivo contenido en el interior de
      cualquier que no est� en la whitelist que es destinado para escaneando.
   - "OLE Firmas" (ole_*). Cotejado contra los contenidos de cada OLE objeto
      que no est� en la whitelist que es destinado para escaneando.
   - "PDF Firmas" (pdf_*). Cotejado contra los contenidos de cada PDF archivo
      que no est� en la whitelist que es destinado para escaneando.
   - "Port�til Ejecutable Secci�nal Firmas" (pe_*). Cotejado contra el MD5 hash
      y el tama�o de cada PE secci�n de cada archivo que no est� en la
      whitelist que es destinado para escaneando.
   - "SWF Firmas" (swf_*). Cotejado contra los contenidos de cada Shockwave
      archivo que no est� en la whitelist que es destinado para escaneando.
   - "Whitelist Firmas" (whitelist_*). Cotejado contra el MD5 hash de los
      contenidos y el tama�o de cada archivo que es destinado para escaneando.
      Cotejados archivos ser� inmune de ser cotejado por el tipo de firma
      mencionado en su entrada de la whitelist.
   - "XML/XDP-Chunk Firmas" (xmlxdp_*). Cotejado contra cualquier XML/XDP
      trozos encontrado dentro de cualquier archivo que no est� en la whitelist
      que es destinado para escaneando.
     (Notar que cualquier de estas firmas pueden estar f�cilmente deshabilitado
      a trav�s de phpmussel.ini).

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

 Esta informaci�n ha sido actualizado 1 Mayo 2015 y es a hoy para todas las
 phpMussel versiones de la dos m�s recientes menores versiones (v0.5-v0.6) al
 momento de escribir esto.

 Ad-Aware                No hay conocidos problemas
 Agnitum                 No hay conocidos problemas
 AhnLab-V3               No hay conocidos problemas
 AntiVir                 No hay conocidos problemas
 Antiy-AVL               No hay conocidos problemas
 Avast                !  Informa como "JS:ScriptSH-inf [Trj]"
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
 McAfee               !  Informa como "New Script.c"
 McAfee-GW-Edition    !  Informa como "New Script.c"
 Microsoft               No hay conocidos problemas
 MicroWorld-eScan        No hay conocidos problemas
 NANO-Antivirus          No hay conocidos problemas
 Norman               !  Informa como "Kryptik.BQS"
 nProtect                No hay conocidos problemas
 Panda                   No hay conocidos problemas
 Qihoo-360               No hay conocidos problemas
 Rising                  No hay conocidos problemas
 Sophos                  No hay conocidos problemas
 SUPERAntiSpyware        No hay conocidos problemas
 Symantec             !  Informa como "WS.Reputation.1"
 TheHacker               No hay conocidos problemas
 TotalDefense            No hay conocidos problemas
 TrendMicro              No hay conocidos problemas
 TrendMicro-HouseCall    No hay conocidos problemas
 VBA32                   No hay conocidos problemas
 VIPRE                   No hay conocidos problemas
 ViRobot                 No hay conocidos problemas


                                     ~ ~ ~


�ltima Actualizaci�n: 20 Mayo 2015 (2015.05.20).
EOF
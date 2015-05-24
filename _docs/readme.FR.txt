      _____  _     _  _____  _______ _     _ _______ _______ _______
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____

                            { ~ ~ ~ FRAN�AIS ~ ~ ~ }
 CONTENU
 1. PR�AMBULE
 2A. COMMENT INSTALLER (POUR WEB SERVEURS)
 2B. COMMENT INSTALLER (POUR CLI)
 3A. COMMENT UTILISER (POUR WEB SERVEURS)
 3B. COMMENT UTILISER (POUR CLI)
 4A. NAVIGATEUR COMMANDES
 4B. CLI (COMMANDE LIGNE INTERFACE)
 5. FICHIERS INCLUS DANS CES EMPAQUETER
 6. CONFIGURATION OPTIONS
 7. SIGNATURE FORMAT
 8. CONNUS PROBL�MES DE COMPATIBILIT�

                                     ~ ~ ~


 1. PR�AMBULE

 Merci pour l'utiliser de phpMusel, un PHP script pour la d�tection de virus,
 malveillants logiciels et autres menaces dans les fichiers t�l�charg�s sur
 votre syst�me partout o� le script est accroch�, bas� sur les signatures de
 ClamAV et autres.

 PHPMUSSEL COPYRIGHT 2013 et au-del� GNU/GPL V.2 par Caleb M (Maikuolan).

 Ce script est un logiciel libre; vous pouvez redistribuer et/ou le modifier
 selon les termes de la GNU General Public License telle que publi�e par la
 Free Software Foundation; soit la version 2 de la Licence, ou (� votre choix)
 toute version ult�rieure. Ce script est distribu� dans l'espoir qu'il sera
 utile, mais SANS AUCUNE GARANTIE, sans m�me la implicite garantie de
 COMMERCIALISATION ou D'ADAPTATION � UN PARTICULIER USAGE. Voir la GNU General
 Public License pour plus de d�tails, situ� dans le "LICENCE" fichier dans le
 "_docs" r�pertoire de l'associ� emballage et un r�f�rentiel pour ce fichier et
 �galement disponible � partir de:
 <http://www.gnu.org/licenses/> <http://opensource.org/licenses/>.

 Un sp�cial merci � ClamAV pour l'inspiration du le projet et pour les
 signatures que ce script utilise, sans qui, le script ne seraient
 probablement pas exister, ou, au mieux, auraient avoir un tr�s limit�
 valeur <http://www.clamav.net/>.

 Un sp�cial merci � Sourceforge et GitHub pour l'h�bergement du projet
 fichiers, situ� � <http://phpmussel.sourceforge.net/> et
 <https://github.com/Maikuolan/phpMussel/>, � Spambot Security pour
 l'h�bergement du phpMussel discussion forums, situ� �
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, et � les sources
 suppl�mentaires d'un certain nombre de signatures utilis�s par phpMussel:
 SecuriteInfo.com <http://www.securiteinfo.com/>, PhishTank
 <http://www.phishtank.com/>, NLNetLabs <http://nlnetlabs.nl/> et autres, et
 merci � tous ceux qui soutiennent le projet, � quelqu'un d'autre que j'ai
 peut-�tre oubli� de mentionner autrement, et � vous, pour l'utiliser du
 script.

 Ce document et son associ� empaqueter peuvent �tre t�l�charg� gratuitement �
 sans frais � partir de:
 - Sourceforge <http://phpmussel.sourceforge.net/>.
 - GitHub <https://github.com/Maikuolan/phpMussel/>.

                                     ~ ~ ~


 2A. COMMENT INSTALLER (POUR WEB SERVEURS)

 J'ai l'intention de simplifier ce processus par la cr�ation d'un programme
 d'installation � l'avenir, mais en attendant, suivez ces instructions pour
 la correcte fonction de phpMussel sur la majorit� de syst�mes et CMS:

 1) Parce que vous lisez ceci, je suppose que vous avez d�j� t�l�charg� une
    archiv�e copie du script, d�compress� son contenu et l'ont assis sur votre
    locale machine. Maintenant, vous devez d�terminer l'appropri� emplacement
    sur votre h�te ou CMS � mettre ces contenus. Un r�pertoire comme
    /public_html/phpmussel/ ou similaire (cependant, il n'est pas question que
    vous choisissez, � condition que c'est quelque part de s�r et quelque part
    que vous �tes heureux avec) sera suffira. Vous avant commencer
    t�l�chargement au serveur, continuer lecture..

 2) Ouvrir "phpmussel.php", cherchez pour la ligne commen�ant par "$vault=",
    et remplacez la string entre guillemets suivantes sur cette ligne avec le
    v�ritable exact emplacement du le r�pertoire "vault" de phpMussel. Vous
    aurez remarqu� un tel dossier dans l'archive que vous avez t�l�charg� (sauf
    si vous sentez � nouveau codage de l'ensemble du script, vous aurez besoin
    � maintenir la m�me structure de fichiers et de r�pertoires comme il �tait
    dans l'origine archive). Ce "vault" r�pertoire devrait �tre d'un niveau
    au-dessus le r�pertoire que le fichier "phpmussel.php" existera po.
    Enregistrer le fichier, fermer.

 3) (En option; Fortement recommand� pour l'avanc�s utilisateurs, mais pas
    recommand� pour les d�butants ou pour les novices): Ouvrir "phpmussel.ini"
    (situ� � l'int�rieur de "vault") - Ce fichier contient toutes les
    directives disponible pour phpMussel. Au-dessus de chaque option devrait
    �tre un bref commentaire d�crivant ce qu'il fait et ce qu'il est pour.
    R�glez ces options comme bon vous semble, selon ce qui est appropri� pour
    votre particuli�re configuration. Enregistrer le fichier, fermer.

 4) T�l�chargez le contenu (phpMussel et ses fichiers) � le r�pertoire vous
    aviez d�cid� plus t�t (vous n'avez pas besoin le readme.XX.txt ou le
    change_log.txt fichiers inclus, mais, surtout, vous devriez t�l�charger
    tous les fichiers sur le serveur).

 5) CMHOD la "vault" r�pertoire � "777". Le principal r�pertoire qui est
    stocker le contenu (celui que vous avez choisi plus t�t), g�n�ralement,
    peut �tre laiss� seul, mais CHMOD �tat devrait �tre v�rifi� si vous avez eu
    probl�mes d'autorisations dans le pass� sur votre syst�me (par d�faut,
    devrait �tre quelque chose comme "755").

 6) Suivant, vous aurez besoin de "crochet" phpMussel � votre syst�me ou CMS.
    Il est plusieurs fa�ons vous pouvez "crochet" phpMussel � votre syst�me ou
    CMS, mais le plus simple est � simplement inclure le script au d�but d'un
    fichier de la base de donn�es de votre syst�me ou CMS (un qui va
    g�n�ralement toujours �tre charg� lorsque quelqu'un acc�de � n'importe
    quelle page sur votre website) utilisant un require ou include commande.
    G�n�ralement, ce sera quelque chose de stock� dans un r�pertoire comme
    "/includes", "/assets" ou "/functions", et il sera souvent nomm� quelque
    chose comme "init.php", "common_functions.php", "functions.php" ou
    similaire. Vous sera besoin � d�terminer qui est le fichier c'est pour
    votre situation. Pour ce faire, ins�rez la ligne de code suivante au d�but
    de ce le noyau fichier et remplacer la string contenue � l'int�rieur des
    guillemets avec l'exacte adresse le fichier "phpmussel.php" (l'adresse
    locale, pas l'adresse HTTP; il ressemblera l'adresse de "vault" mentionn�
    pr�c�demment).

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Enregistrer le fichier, fermer, r�t�l�charger.

 7) � ce stade, vous avez fini! Cependant, vous devriez probablement tester ce
    pour s'assurer qu'il fonctionne correctement. Pour tester les protections,
    essayez de t�l�charger les tester fichiers inclus dans le empaqueter sous
    "_testfiles" � votre website par votre habituelles navigateur bas� m�thodes
    de t�l�chargement. Si tout fonctionne correctement, un message devrait
    appara�tre � partir de phpMussel confirmant que le t�l�chargement a �t�
    bloqu� avec succ�s. Si rien ne s'affiche, quelque chose ne fonctionne pas
    correctement. Si vous utilisez d'avanc�es fonctions ou si vous utilisez
    l'autres types d'analyse possibles avec l'outil, je vous sugg�re de
    l'essayer avec ceux pour s'assurer qu'il fonctionne comme pr�vu, aussi.

                                     ~ ~ ~


 2B. COMMENT INSTALLER (POUR CLI)

 J'ai l'intention de simplifier ce processus par la cr�ation d'un programme
 d'installation � l'avenir, mais en attendant, suivez ces instructions pour
 rendant phpMussel dispos� de travailler avec CLI (�tre conscient que, � ce
 stade, CLI support est uniquement pour les Windows syst�mes; Linux et d'autres
 syst�mes seront bient�t arriver � une ult�rieure version de phpMussel):

 1) Parce que vous lisez ceci, je suppose que vous avez d�j� t�l�charg� une
    archiv�e copie du script, d�compress� son contenu et l'ont assis sur votre
    locale machine. Lorsque vous avez d�termin� que vous �tes satisfait sur
    l'emplacement choisi pour phpMussel, continuer.

 2) phpMussel exige php d'�tre install� sur l'h�te ordinateur afin d'ex�cuter.
    Si vous n'avez pas de php install� sur votre machine, s'il vous pla�t
    installer php sur votre machine, suivant les instructions fournies par le
    programme d'installation de php.

 2) Ouvrir "phpmussel.php", cherchez pour la ligne commen�ant par "$vault=",
    et remplacez la string entre guillemets suivantes sur cette ligne avec le
    v�ritable exact emplacement du le r�pertoire "vault" de phpMussel. Vous
    aurez remarqu� un tel dossier dans l'archive que vous avez t�l�charg� (sauf
    si vous sentez � nouveau codage de l'ensemble du script, vous aurez besoin
    � maintenir la m�me structure de fichiers et de r�pertoires comme il �tait
    dans l'origine archive). Ce "vault" r�pertoire devrait �tre d'un niveau
    au-dessus le r�pertoire que le fichier "phpmussel.php" existera po.
    Enregistrer le fichier, fermer.

 4) (En option; Fortement recommand� pour l'avanc�s utilisateurs, mais pas
    recommand� pour les d�butants ou pour les novices): Ouvrir "phpmussel.ini"
    (situ� � l'int�rieur de "vault") - Ce fichier contient toutes les
    directives disponible pour phpMussel. Au-dessus de chaque option devrait
    �tre un bref commentaire d�crivant ce qu'il fait et ce qu'il est pour.
    R�glez ces options comme bon vous semble, selon ce qui est appropri� pour
    votre particuli�re configuration. Enregistrer le fichier, fermer.

 5) (En option) Vous pouvez faire utilisant phpMussel en CLI mode plus facile
    pour vous-m�me par la cr�ation d'un fichier de commandes pour automatique
    charger php et phpMussel. Pour ce faire, ouvrir un �diteur de texte comme
    Notepad ou Notepad++, tapez le complet chemin vers le "php.exe" fichier
    dans le r�pertoire de votre installation de PHP, suivi d'un espace, suivi
    par le complet chemin vers le "phpmussel.php" fichier dans le r�pertoire de
    votre installation de phpMussel, enregistrer le fichier avec un ".bat"
    suffixe quelque part que vous trouverez facile, et double-cliquez sur ce
    fichier pour ex�cuter phpMussel � l'avenir.

 6) � ce stade, vous avez fini! Mais, vous devriez probablement tester ce
    pour s'assurer qu'il fonctionne correctement. Pour tester phpMussel,
    ex�cuter phpMussel et essayer d'analyser le "_testfiles" r�pertoire fourni
    avec le paquet.

                                     ~ ~ ~


 3A. COMMENT UTILISER (POUR WEB SERVEURS)

 phpMussel est pr�vu � �tre un script qui fonctionnera correctement d�s la
 bo�te avec un minimum niveau des exigences de votre part: Une fois qu'il a �t�
 install�, au fond, il devrait simplement travailler.

 Num�risation de fichiers t�l�charg� est automatis�e et activ�e par d�faut,
 donc rien n'est requise de votre part pour cette particuli�re fonction.

 Cependant, vous �tes �galement capable de instruire phpMussel � rechercher des
 fichiers, r�pertoires ou archives que vous sp�cifiez implicitement. Pour ce
 faire, d'abord, vous devez assurer que la appropri�e configuration est r�gl�e
 dans le phpmussel.ini fichier (cleanup doit �tre d�sactiv�), et lorsque fini,
 dans un php fichier qui est li� � phpMussel, utiliser la fonction suivante
 dans votre code:

 phpMussel($quoi_a_recherche,$sortie_type,$sortie_platitude);

 O�:
 - $quoi_a_recherche est une string ou un tableau, pointant � un cible fichier,
   un cible r�pertoire ou un tableau de cibles fichiers et/ou cibles
   r�pertoires.
 - $sortie_type est un entier, indiquant le format dans lequel les r�sultats de
   l'analyse doivent �tre retour. Une valeur de 0 instruit que la fonction
   d'affichage des r�sultats comme un entier (un retourn� r�sultat de -2
   indique que corrompues donn�es �tait d�tect� lors de l'analyse et donc
   l'analyse n'ont pas r�ussi � compl�ter, -1 indique que les extensions ou
   addons requis par PHP pour ex�cuter l'analyse sont manquaient et donc
   l'analyse n'ont pas r�ussi � compl�ter, 0 indique qu'il n'existe pas cible �
   analyser et donc il n'y avait rien � analyser, 1 indique que la cible �tait
   analys� avec succ�s et aucun probl�me n'�t� d�tect�e, et 2 indique que la
   cible �tait analys� avec succ�s et probl�mes ont �t� d�tect�s). Une valeur
   de 1 indique � la fonction pour renvoyer les r�sultats sous forme de texte
   lisible par l'homme. Une valeur de 2 indique � la fonction pour renvoyer les
   r�sultats sous forme de texte lisible par l'homme et pour exporter les
   r�sultats � une globale variable. Cette variable est facultative, 0 par
   d�faut.
 - $sortie_platitude est un entier, indiquant si les r�sultats pourront �tre
   retourn�s comme un tableau ou pas. Normalement, si la cible de l'analyse
   contenue plusieurs articles (par exemple, si un r�pertoire ou un tableau)
   les r�sultats seront retourn�s dans un tableau (d�faut valeur de 0). Une
   valeur de 1 instruit la fonction pour imploser tous tableaux avant l'entr�e,
   r�sultant en une aplatie string contenant les r�sultats � �tre retourner.
   Cette variable est facultative, 0 par d�faut.

 Exemples:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Retours quelque chose comme �a (comme une string):
    Wed, 16 Sep 2013 02:49:46 +0000 Commenc�.
    > V�rification '/user_name/public_html/my_file.html':
    -> Pas probl�me trouv�.
    Wed, 16 Sep 2013 02:49:47 +0000 Termin�.

 Pour un complet itin�raire de signatures que sera utilis� par phpMussel pour
 l'analyse et la fa�on dont il g�re ces signatures, r�f�rer � la Signature
 Format section de ce README fichier.

 Si vous rencontrez des faux positifs, si vous rencontrez quelque chose nouveau
 que vous pensez doit �tre bloqu�, ou pour toute autre chose en ce qui concerne
 les signatures, s'il vous pla�t, contactez moi � ce sujet afin que je puisse
 effectuer les n�cessaires changements, dont, si vous ne contactez moi pas,
 j'ai peut n'�tre pas conscient.

 Pour d�sactiver les signatures qui sont incluent avec phpMussel (comme si vous
 rencontrez un faux positif sp�cifique � vos besoins dont ne devrait
 normalement pas �tre retir� � partir de rationaliser), r�f�rer aux les notes
 de la liste grise dans le Navigateur Commandes section de ce README fichier.

 En plus de la d�faut analyse de fichier t�l�chargement et la facultative
 analyse d'autres fichiers et/ou r�pertoires sp�cifi�s par la fonction
 ci-dessus, inclus dans phpMussel est une fonction destin�e pour l'analyse du
 corps des courriels messages. Cette fonction se comporte comme la standard
 phpMussel() fonction, mais se concentre uniquement sur la correspondance
 contre les ClamAV courriels bas�es signatures. Je n'ai pas attach� ces
 signatures dans la standard phpMussel() fonction, parce que il est hautement
 improbable que vous auriez trouver le corps d'un entrant message dans le
 besoin de l'analyse dans un fichier t�l�chargement cibl� d'un page o�
 phpMussel est accroch�, et ainsi, pour lier ces signatures dans la phpMussel()
 fonction serait redondant. Cependant, � ce que ledit, ayant une distincte
 fonction pour correspondre encontre ces signatures pourrait s'av�rer
 extr�mement utile pour quelque, surtout pour ceux dont CMS ou syst�me webfront
 est en quelque sorte li� � leur messagerie syst�me et pour ceux dont analyser
 leurs courriels � travers un script php dont ils pourraient s'accrocher dans
 phpMussel. Configuration pour cette fonction, comme tous les autres, est
 contr�l� par le phpmussel.ini fichier. Pour utiliser cette fonction (vous
 aurez besoin de faire votre propre impl�mentation), dans un php fichier qui
 est accroch� � phpMussel, utiliser ce fonction dans votre code:

 phpMussel_mail($corps);

 O� $corps est le corps de le courriel que vous souhaitez d'analyser (plus,
 vous pouvez essayer d'analyser nouveaux forum messages, l'entrants messages de
 votre online contact page ou similaire). Si une erreur s'emp�chant la fonction
 d'achever son analyse, une valeur de -1 sera retourn�. Si la fonction a
 termin� son analyse et ne correspond pas � rien, une valeur de 0 sera retourn�
 (indiquant pas infect�). Si, cependant, la fonction correspond � quelque
 chose, une string sera retourn�e contenant un message d�clarant ce qu'il a
 identifi�.

 En plus de ce qui pr�c�de, si vous regardez le source code, vous peut
 remarquerez la fonction phpMusselD() et phpMusselR(). Ces fonctions sont
 sous-fonctions de phpMussel(), et ne devrait pas �tre appel� directement �
 l'ext�rieur de cette principale fonction (pas en raison d'ind�sirables
 effets.. Plus-si, simplement parce que ce serait sans utilit�, et tr�s
 probablement ne sera pas r�ellement fonctionner correctement de toute fa�on).

 Il ya beaucoup autres contr�les et fonctions disponibles dans phpMussel pour
 votre usage, aussi. Pour toutes ces contr�les et fonctions dont, sur la fin de
 cette section de la README, n'ont pas encore �t� document�, s'il vous pla�t,
 continuer � lire et r�f�rer � la Navigateur Commandes section de ce README
 fichier.

                                     ~ ~ ~


 3B. COMMENT UTILISER (POUR CLI)

 S'il vous pla�t, r�f�rer � la "COMMENT INSTALLER (POUR CLI)" section de ce
 README fichier.

 Soyez conscient que, bien que avenirs versions de phpMussel devraient soutenir
 d'autres syst�mes, � ce moment, phpMussel CLI mode support est uniquement
 optimis� pour l'utilisation sur le Windows bas�e syst�mes (vous pouvez, bien
 s�r, essayer sur d'autres syst�mes, mais je ne peux pas garantir que �a va
 fonctionner comme pr�vu).

 Aussi soyez conscient que phpMussel est pas la fonctionnel �quivalent d'une
 complet anti-virus suite, et contrairement conventionnelles anti-virus suites,
 ne surveille pas la active m�moire ou d�tecter les virus sur la vol�e! Il
 seulement d�tecte les virus contenus dans les fichiers que vous explicitement
 sp�cifier pour d'analyse.

                                     ~ ~ ~


 4A. NAVIGATEUR COMMANDES

 Apr�s phpMussel a �t� install� et est fonctionner correctement sur votre
 syst�me, si vous avez d�fini les variables script_password et logs_password
 dans votre configuration fichier, vous sera pouvoir d'effectuer un certain
 nombre de administratives fonctions et entr�e un nombre de commandes �
 phpMussel par votre navigateur. La raison de ces mots de passe doivent �tre
 defini afin de permettre � ces navigateur contr�les est pour assurer ad�quate
 s�curit�, l'ad�quate protection de ces navigateur contr�les et faire en sorte
 une m�thode existe pour ceux navigateur contr�le � �tre enti�rement d�sactiv�
 si elles ne sont pas souhait�es par vous et/ou autres
 webmasters/administrateurs dont sont l'utiliser phpMussel. Ainsi, en d'autres
 termes, pour activer ces contr�les, d�finir un mot de passe, et pour
 d�sactiver ces contr�les, d�finir aucun mot de passe. Comme alternatif, si
 vous choisir d'activer ces contr�les et puis choisir de d�sactiver ces
 contr�les � une ult�rieure date, il existe une commande � faire ce (tel peut
 �tre utile si vous effectuer certaines actions vous sentez pourrait
 compromettre les mots de pass que vous avez d�l�gu� et besoin de rapidement
 d�sactiver ces contr�les sans modifier votre configuration fichier).

 Quelques raisons pour lesquelles vous -devriez- permettre � ces contr�les:
 - Fournit une m�thode � liste grise les signatures sur la vol�e dans des cas
   comme lorsque vous d�couvrez une signature qui produit un faux positif
   tandis le t�l�chargement de fichiers � votre syst�me et vous n'avez pas le
   temps � manuellement modifier et r�t�l�charger votre liste grise fichier.
 - Fournit une m�thode pour vous � permettre � quelqu'un d'autre que vous pour
   contr�ler votre copie de phpMussel sans la implicite n�cessit� � donner de
   leur acc�s � FTP.
 - Fournit une m�thode � fournir contr�l� acc�s � vos journaux fichiers.
 - Fournit un facile m�thode � r�actualiser phpMussel quand une r�actualiser
   est disponibles.
 - Fournit une m�thode pour vous � surveiller phpMussel quand l'acc�s de FTP ou
   d'autres conventionnelles points d'acc�s pour surveillance de phpMussel ne
   sont pas disponibles.

 Quelques raisons pour lesquelles vous -ne devriez pas- permettre � ces
 contr�les:
 - Fournit un potentiel vecteur pour attaquants et ind�sirables � d�terminer si
   vous utilisez phpMussel ou pas (quoique, cela pourrait �tre positif ou
   n�gatif, en lieu du point de vue) par le biais d'aveugl�ment envoyer les
   commandes aux serveurs comme m�thode � sonder. D'une part, cela pourrait
   d�courager les attaquants de cibler votre syst�me s'ils apprennent que vous
   utilisez phpMussel, en supposant qu'ils sondage parce que leur m�thode
   d'attaque est rendu inefficace en raison de l'utilisation de phpMussel.
   Mais, de l'autre part, si certains impr�vu et actuellement inconnue exploit
   dans phpMussel uo un avenir version de celui-ci vient � la lumi�re, et si
   elle pourrait fournir un vecteur d'attaque, un positif r�sultat d'une telle
   sondage pourrait effectivement encourager les attaquants � cibler votre
   syst�me.
 - Si vos d�l�gu�s mots de passe ont �t� compromises, sans �tre chang�,
   pourrait fournir un m�thode pour un attaquant � contourner les signatures
   que peuvent �tre autrement normalement emp�chent leurs attaques de r�ussir,
   ou m�me potentiellement d�sactiver phpMussel compl�tement, ainsi fournissant
   un th�orique m�thode de rendre l'efficacit� de phpMussel avenu.

 De toute fa�on, ind�pendamment de que vous choisissez, le choix est finalement
 v�tre. Par d�faut, ces contr�les seront d�sactiv�s, mais avoir une r�flexion �
 ce sujet, et si vous d�cidez que vous voulez ces, cette section explique
 comment activer et comment utiliser ces.

 Une liste de disponible navigateur commandes:

 scan_log
   Mot de passe requis: logs_password
   Autre exigences: scan_log doit �tre d�fini.
   Param�tres requis: (aucun)
   Param�tres optionnels: (aucun)
   Exemple: ?logspword=[logs_password]&phpmussel=scan_log
   ~
   Quel est-il: Imprime le contenu de votre scan_log fichier � l'�cran.
   ~
 scan_kills
   Mot de passe requis: logs_password
   Autre exigences: scan_kills doit �tre d�fini.
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?logspword=[logs_password]&phpmussel=scan_kills
   ~
   Quel est-il: Imprime le contenu de votre scan_kills fichier � l'�cran.
   ~
 controls_lockout
   Mot de passe requis: logs_password OU script_password
   Autre exigences: (aucun)
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple 1: ?logspword=[logs_password]&phpmussel=controls_lockout
   Exemple 2: ?pword=[script_password]&phpmussel=controls_lockout
   ~
   Quel est-il: D�sactiver/verrouille tous les navigateur contr�les. Cela
                devrait �tre utilis� si vous pensez que vos mots de passe ont
                �t� compromis (cela peut arriver si vous utilisez ces commandes
                � partir d'un ordinateur qui n'est pas s�curis� et/ou n'est pas
                digne de confiance). controls_lockout fonctionne par cr�ant un
                fichier, controls.lck, dans votre vo�te, dont phpMussel sera
                v�rifi� avant d'effectuer commandes de toute nature. Apr�s,
                pour r�activer les contr�les, vous devez manuellement supprimer
                le controls.lck fichier par FTP ou similaire.
   ~
 disable
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=disable
   ~
   Quel est-il: D�sactiver phpMussel. Cela devrait �tre utilis� si vous
                r�actualiser ou faire changements � votre syst�me ou si vous
                installez un nouveau logiciel ou modules � votre syst�me dont
                sera ou pourrait potentiellement d�clencher faux positifs.
                Aussi, Cela devrait �tre utilis� si vous rencontrez probl�mes
                avec phpMussel mais ne veulent pas � supprimer de votre
                syst�me. Si c'est le cas, pour r�activer phpMussel, utiliser
                "enable".
   ~
 enable
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=enable
   ~
   Quel est-il: R�activer phpMussel. Cela devrait �tre utilis� si vous avez
                pr�c�demment d�sactiv� phpMussel utilisant "disable" et vous
                voulez � r�activer ce.
   ~
 update
   Mot de passe requis: script_password
   Autre exigences: update.dat and update.inc must exist.
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=update
   ~
   Quel est-il: V�rifie pour nouvelles versions de phpMussel et ses signatures.
                Si quelque chose est trouv�, il va tenter � t�l�charger et
                installer les nouveaux fichiers. S'il est ne parvient pas �
                v�rifier, il sera annulerait. Les r�sultats du processus sont
                imprim�s � l'�cran. Je recommande v�rifier au moins une fois
                par mois afin d'assurer que vos signatures et votre copie de
                phpMussel sont la derni�re disponible. (sauf, bien s�r, vous
                t�l�charger et installer les derniers fichiers manuellement,
                dont, j'aussi recommande v�rifier au moins une fois par mois).
                V�rification de plus de deux fois par mois est probablement
                inutile, en tenant compte que je (au moment d'�crire ces)
                travaille sur ce projet par moi-m�me et je suis tr�s peu
                probable d'�tre produire nouveaux fichiers plus fr�quemment que
                cela (ni je ne particuli�rement pas vouloir �, pour la
                plupart).
   ~
 greylist
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Param�tres requis: [Name of signature to be greylisted]
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist&musselvar=[Signature]
   ~
   Quel est-il: Ajouter une signature � la liste grise.
   ~
 greylist_clear
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist_clear
   ~
   Quel est-il: Efface la totalit� de la liste grise.
   ~
 greylist_show
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Param�tres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist_show
   ~
   Quel est-il: Imprime le contenu de la liste grise � l'�cran.
   ~

                                     ~ ~ ~


 4B. CLI (COMMANDE LIGNE INTERFACE)

 phpMussel peut �tre ex�cut� comme un interactif fichier analyseur en CLI mode
 dans windows. R�f�rer � la "COMMENT INSTALLER (POUR CLI)" section de ce readme
 fichier pour plus d�tails.

 Pour une liste des disponibles CLI commandes, � l'invite CLI, tapez �c�, et
 appuyez sur Entr�e.

                                     ~ ~ ~


 5. FICHIERS INCLUS DANS CES EMPAQUETER

 Voici une liste de tous les fichiers inclus dans phpMussel dans son natif
 �tat, tous les fichiers qui peuvent �tre potentiellement cr��es � la suite de
 l'utilisation de ce script, avec une br�ve description de ce que tous ces
 fichiers sont pour.

 /phpmussel.php (Script, Inclu)
    phpMussel chargement fichier. Charge le principal script et etc. C'est ce
    que vous �tes cens� �tre accrochage dans � (essentiel)!
    ~
 /web.config (Autre, Inclu)
    Un ASP.NET configuration fichier (dans ce cas, pour prot�ger de la "/vault"
    r�pertoire contre d'�tre consult� par des non autoris�e sources dans le cas
    o� le script est install� sur un serveur bas� sur les ASP.NET
    technologies).
    ~
 /_docs/ (Directory)
    Documentation r�pertoire (contient divers fichiers).
    ~
 /_docs/change_log.txt (Documentation, Inclu)
    Un enregistrement des modifications apport�es au script entre les
    diff�rentes versions (pas n�cessaire pour le bon fonctionnement du script).
    ~
 /_docs/readme.DE.txt (Documentation, Inclu); DEUTSCH
 /_docs/readme.EN.txt (Documentation, Inclu); ENGLISH
 /_docs/readme.ES.txt (Documentation, Inclu); ESPA�OL
 /_docs/readme.FR.txt (Documentation, Inclu); FRAN�AIS
 /_docs/readme.ID.txt (Documentation, Inclu); BAHASA INDONESIA
 /_docs/readme.IT.txt (Documentation, Inclu); ITALIANO
 /_docs/readme.NL.txt (Documentation, Inclu); NEDERLANDSE
 /_docs/readme.PT.txt (Documentation, Inclu); PORTUGU�S
    Le README fichiers (par exemple; le fichier vous �tes en cours de lire).
    ~
 /_docs/signatures_tally.txt (Documentation, Inclu)
    D�compte de signatures inclus (pas n�cessaire pour le bon fonctionnement du
    script).
    ~
 /_testfiles/ (Directory)
    Test fichiers r�pertoire (contient divers fichiers).
    Tous les fichiers contenus sont des fichiers � test si phpMussel a �t�
    correctement install� sur votre syst�me, et vous n'avez pas besoin de
    t�l�charger ce r�pertoire ou l'un de ses fichiers, sauf si faire ces tests.
    ~
 /_testfiles/ascii_standard_testfile.txt (Test fichier, Inclu)
    Test fichier � test phpMussel normalis� ASCII signatures.
    ~
 /_testfiles/coex_testfile.rtf (Test fichier, Inclu)
    Test fichier � test phpMussel complexe �tendu signatures.
    ~
 /_testfiles/exe_standard_testfile.exe (Test fichier, Inclu)
    Test fichier � test phpMussel PE signatures.
    ~
 /_testfiles/general_standard_testfile.txt (Test fichier, Inclu)
    Test fichier � test phpMussel g�n�rales signatures.
    ~
 /_testfiles/graphics_standard_testfile.gif (Test fichier, Inclu)
    Test fichier � test phpMussel graphiques signatures.
    ~
 /_testfiles/html_standard_testfile.txt (Test fichier, Inclu)
    Test fichier � test phpMussel normalis� HTML signatures.
    ~
 /_testfiles/md5_testfile.txt (Test fichier, Inclu)
    Test fichier � test phpMussel MD5 signatures.
    ~
 /_testfiles/metadata_testfile.txt.gz (Test fichier, Inclu)
    Test fichier � test phpMussel m�tadonn�es signatures et pour tester GZ
    fichier support sur votre syst�me.
    ~
 /_testfiles/metadata_testfile.zip (Test fichier, Inclu)
    Test fichier � test phpMussel m�tadonn�es signatures et pour tester ZIP
    fichier support sur votre syst�me.
    ~
 /_testfiles/ole_testfile.ole (Test fichier, Inclu)
    Test fichier � test phpMussel OLE signatures.
    ~
 /_testfiles/pdf_standard_testfile.pdf (Test fichier, Inclu)
    Test fichier � test phpMussel PDF signatures.
    ~
 /_testfiles/pe_sectional_testfile.exe (Test fichier, Inclu)
    Test fichier � test phpMussel PE Sectional signatures.
    ~
 /_testfiles/swf_standard_testfile.swf (Test fichier, Inclu)
    Test fichier � test phpMussel SWF signatures.
    ~
 /_testfiles/xdp_standard_testfile.xdp (Test fichier, Inclu)
    Test fichier � test phpMussel XML/XDP morceaux signatures.
    ~
 /vault/ (R�pertoire)
    Vo�te r�pertoire (contient divers fichiers).
    ~
 /vault/quarantine/ (R�pertoire)
    Quarantaine r�pertoire (contient des fichiers de la quarantaine).
    ~
 /vault/quarantine/.htaccess (Autre, Inclu)
    Un hypertexte acc�s fichier (dans ce cas, pour prot�ger les sensibles
    fichiers appartenant au script contre �tre consult� par non autoris�es
    sources).
    ~
 /vault/.htaccess (Autre, Inclu)
    Un hypertexte acc�s fichier (dans ce cas, pour prot�ger les sensibles
    fichiers appartenant au script contre �tre consult� par non autoris�es
    sources).
    ~
 /vault/ascii_clamav_regex.cvd (Signatures, Inclus)
 /vault/ascii_clamav_regex.map (Signatures, Inclus)
 /vault/ascii_clamav_standard.cvd (Signatures, Inclus)
 /vault/ascii_clamav_standard.map (Signatures, Inclus)
 /vault/ascii_custom_regex.cvd (Signatures, Inclus)
 /vault/ascii_custom_standard.cvd (Signatures, Inclus)
 /vault/ascii_mussel_regex.cvd (Signatures, Inclus)
 /vault/ascii_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour normalis� ASCII signatures.
    N�cessaire si la normalis� ASCII option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/coex_clamav.cvd (Signatures, Inclus)
 /vault/coex_custom.cvd (Signatures, Inclus)
 /vault/coex_mussel.cvd (Signatures, Inclus)
    Fichiers pour le Complexe �tendu signatures.
    N�cessaire si le complexe �tendu option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/elf_clamav_regex.cvd (Signatures, Inclus)
 /vault/elf_clamav_regex.map (Signatures, Inclus)
 /vault/elf_clamav_standard.cvd (Signatures, Inclus)
 /vault/elf_clamav_standard.map (Signatures, Inclus)
 /vault/elf_custom_regex.cvd (Signatures, Inclus)
 /vault/elf_custom_standard.cvd (Signatures, Inclus)
 /vault/elf_mussel_regex.cvd (Signatures, Inclus)
 /vault/elf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour ELF signatures.
    N�cessaire si l'ELF signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/exe_clamav_regex.cvd (Signatures, Inclus)
 /vault/exe_clamav_regex.map (Signatures, Inclus)
 /vault/exe_clamav_standard.cvd (Signatures, Inclus)
 /vault/exe_clamav_standard.map (Signatures, Inclus)
 /vault/exe_custom_regex.cvd (Signatures, Inclus)
 /vault/exe_custom_standard.cvd (Signatures, Inclus)
 /vault/exe_mussel_regex.cvd (Signatures, Inclus)
 /vault/exe_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Portable Executable fichier (EXE) signatures.
    N�cessaire si l'EXE signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/filenames_clamav.cvd (Signatures, Inclus)
 /vault/filenames_custom.cvd (Signatures, Inclus)
 /vault/filenames_mussel.cvd (Signatures, Inclus)
    Fichiers pour filename signatures.
    N�cessaire si le filename signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/general_clamav_regex.cvd (Signatures, Inclus)
 /vault/general_clamav_regex.map (Signatures, Inclus)
 /vault/general_clamav_standard.cvd (Signatures, Inclus)
 /vault/general_clamav_standard.map (Signatures, Inclus)
 /vault/general_custom_regex.cvd (Signatures, Inclus)
 /vault/general_custom_standard.cvd (Signatures, Inclus)
 /vault/general_mussel_regex.cvd (Signatures, Inclus)
 /vault/general_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour g�n�ral signatures.
    N�cessaire si le g�n�ral signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/graphics_clamav_regex.cvd (Signatures, Inclus)
 /vault/graphics_clamav_regex.map (Signatures, Inclus)
 /vault/graphics_clamav_standard.cvd (Signatures, Inclus)
 /vault/graphics_clamav_standard.map (Signatures, Inclus)
 /vault/graphics_custom_regex.cvd (Signatures, Inclus)
 /vault/graphics_custom_standard.cvd (Signatures, Inclus)
 /vault/graphics_mussel_regex.cvd (Signatures, Inclus)
 /vault/graphics_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour graphiques signatures.
    N�cessaire si le graphiques signatures option dans phpmussel.ini est
    activ�e. Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/greylist.csv (Signatures, Inclus/Cr��s)
    CSV de grise list� signatures indiquant pour phpMussel qui signatures il
    faut ignorer (fichier recr�� automatiquement si supprim�).
    ~
 /vault/hex_general_commands.csv (Signatures, Inclus)
    Hex-cod� CSV de g�n�raux commande d�tections optionnellement utilis�s par
    phpMussel. N�cessaire si l'option de g�n�ral commande d�tection dans
    phpmussel.ini est activ�e. Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/html_clamav_regex.cvd (Signatures, Inclus)
 /vault/html_clamav_regex.map (Signatures, Inclus)
 /vault/html_clamav_standard.cvd (Signatures, Inclus)
 /vault/html_clamav_standard.map (Signatures, Inclus)
 /vault/html_custom_regex.cvd (Signatures, Inclus)
 /vault/html_custom_standard.cvd (Signatures, Inclus)
 /vault/html_mussel_regex.cvd (Signatures, Inclus)
 /vault/html_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour normalis� HTML signatures.
    N�cessaire si la normalis� HTML option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/lang.inc (Script, Inclu)
    phpMussel Langue Donn�es; Obligatoire pour les capacit�s multilingues.
    ~
 /vault/macho_clamav_regex.cvd (Signatures, Inclus)
 /vault/macho_clamav_regex.map (Signatures, Inclus)
 /vault/macho_clamav_standard.cvd (Signatures, Inclus)
 /vault/macho_clamav_standard.map (Signatures, Inclus)
 /vault/macho_custom_regex.cvd (Signatures, Inclus)
 /vault/macho_custom_standard.cvd (Signatures, Inclus)
 /vault/macho_mussel_regex.cvd (Signatures, Inclus)
 /vault/macho_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Mach-O signatures.
    N�cessaire si le Mach-O signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/mail_clamav_regex.cvd (Signatures, Inclus)
 /vault/mail_clamav_regex.map (Signatures, Inclus)
 /vault/mail_clamav_standard.cvd (Signatures, Inclus)
 /vault/mail_clamav_standard.map (Signatures, Inclus)
 /vault/mail_custom_regex.cvd (Signatures, Inclus)
 /vault/mail_custom_standard.cvd (Signatures, Inclus)
 /vault/mail_mussel_regex.cvd (Signatures, Inclus)
 /vault/mail_mussel_standard.cvd (Signatures, Inclus)
 /vault/mail_mussel_standard.map (Signatures, Inclus)
    Fichiers pour signatures utilis�es par la phpMussel_mail() fonction.
    N�cessaire si la phpMussel_mail() fonction est utilis� en aucune fa�on.
    Peut enlever si elle n'est pas utilis�e.
    ~
 /vault/md5_clamav.cvd (Signatures, Inclus)
 /vault/md5_custom.cvd (Signatures, Inclus)
 /vault/md5_mussel.cvd (Signatures, Inclus)
    Fichiers pour MD5 bas� signatures.
    N�cessaire si le MD5 signatures option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/metadata_clamav.cvd (Signatures, Inclus)
 /vault/metadata_custom.cvd (Signatures, Inclus)
 /vault/metadata_mussel.cvd (Signatures, Inclus)
    Fichiers pour m�tadonn�es d'archives signatures.
    N�cessaire si le m�tadonn�es d'archives option dans phpmussel.ini est
    activ�e. Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/ole_clamav_regex.cvd (Signatures, Inclus)
 /vault/ole_clamav_regex.map (Signatures, Inclus)
 /vault/ole_clamav_standard.cvd (Signatures, Inclus)
 /vault/ole_clamav_standard.map (Signatures, Inclus)
 /vault/ole_custom_regex.cvd (Signatures, Inclus)
 /vault/ole_custom_standard.cvd (Signatures, Inclus)
 /vault/ole_mussel_regex.cvd (Signatures, Inclus)
 /vault/ole_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour OLE signatures.
    N�cessaire si l'OLE signatures option dans phpmussel.ini est activ�e. Peut
    enlever si l'option est d�sactiv�e.
    ~
 /vault/pdf_clamav_regex.cvd (Signatures, Inclus)
 /vault/pdf_clamav_regex.map (Signatures, Inclus)
 /vault/pdf_clamav_standard.cvd (Signatures, Inclus)
 /vault/pdf_clamav_standard.map (Signatures, Inclus)
 /vault/pdf_custom_regex.cvd (Signatures, Inclus)
 /vault/pdf_custom_standard.cvd (Signatures, Inclus)
 /vault/pdf_mussel_regex.cvd (Signatures, Inclus)
 /vault/pdf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour PDF signatures.
    N�cessaire si le PDF signatures option dans phpmussel.ini est activ�e. Peut
    enlever si l'option est d�sactiv�e.
    ~
 /vault/pe_clamav.cvd (Signatures, Inclus)
 /vault/pe_custom.cvd (Signatures, Inclus)
 /vault/pe_mussel.cvd (Signatures, Inclus)
    Fichiers pour PE Sectional signatures.
    N�cessaire si le PE Sectional signatures option dans phpmussel.ini est
    activ�e. Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/phpmussel.inc (Script, Inclu)
    phpMussel Principal Script; Le principal corps de phpMussel (essentiel)!
    ~
 /vault/phpmussel.ini (Autre, Inclu)
    phpMussel Configuration fichier; Contient toutes les configuration options
    de phpMussel, diriger comment faire fonctionner correctement (essentiel)!
    ~
 /vault/scan_log.txt *(Logfile, Cr��)
    Un enregistrement de tout analys� par phpMussel.
    ~
 /vault/scan_kills.txt *(Logfile, Cr��)
    Les r�sultats de chaque fichier t�l�chargement bloqu�/tu�s par phpMussel.
    ~
 /vault/swf_clamav_regex.cvd (Signatures, Inclus)
 /vault/swf_clamav_regex.map (Signatures, Inclus)
 /vault/swf_clamav_standard.cvd (Signatures, Inclus)
 /vault/swf_clamav_standard.map (Signatures, Inclus)
 /vault/swf_custom_regex.cvd (Signatures, Inclus)
 /vault/swf_custom_standard.cvd (Signatures, Inclus)
 /vault/swf_mussel_regex.cvd (Signatures, Inclus)
 /vault/swf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Shockwave signatures.
    N�cessaire si le Shockwave signatures option dans phpmussel.ini est
    activ�e. Peut enlever si l'option est d�sactiv�e.
    ~
 /vault/switch.dat (Other, Included)
    Contr�le et d�finit certaines variables.
    ~
 /vault/template.html (Autre, Inclu)
    phpMussel mod�le fichier; Mod�le pour l'HTML sortie produit par phpMussel
    pour son bloqu�s fichiers t�l�chargement message (le message vu par
    l'envoyeur).
    ~
 /vault/update.dat (Autre, Inclu)
    Fichier contenant les version informations pour le script et les signatures
    de phpMussel. Si jamais vous voulez � r�actualiser automatiquement
    phpMussel ou r�actualiser phpMusel par votre navigateur, ce fichier est
    indispensable.
    ~
 /vault/update.inc (Script, Inclu)
    phpMussel R�actualiser Script; Requis pour automatique r�actualisation et
    pour r�actualisation phpMussel par votre navigateur, mais n'est pas
    autrement requise.
    ~
 /vault/whitelist_clamav.cvd (Signatures, Inclus)
 /vault/whitelist_custom.cvd (Signatures, Inclus)
 /vault/whitelist_mussel.cvd (Signatures, Inclus)
    Fichier sp�cifique blanche liste.
    N�cessaire si l'option de blanche liste dans phpmussel.ini est activ�e et
    si vous souhaitez avoir sp�cifiques fichiers en le blanche liste. Peut
    enlever si l'option est d�sactiv�e ou si vous n'avez pas besoin de blanche
    liste.
    ~
 /vault/xmlxdp_clamav_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_clamav_regex.map (Signatures, Inclus)
 /vault/xmlxdp_clamav_standard.cvd (Signatures, Inclus)
 /vault/xmlxdp_clamav_standard.map (Signatures, Inclus)
 /vault/xmlxdp_custom_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_custom_standard.cvd (Signatures, Inclus)
 /vault/xmlxdp_mussel_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour XML/XDP morceaux signatures.
    N�cessaire si le XML/XDP morceaux option dans phpmussel.ini est activ�e.
    Peut enlever si l'option est d�sactiv�e.
    ~

 * Noms du fichiers peut varier bas� sur configuration stipulations (dans
   phpmussel.ini).

 = CONCERNANT LES SIGNATURES FICHIERS =
    CVD est un acronyme pour "ClamAV Virus Definitions", en r�f�rence � la
    fa�on ClamAV r�f�re � ses signatures et � l'utilisation de ces signatures
    en phpMussel; Les fichiers terminant par "CVD" contiennent signatures.
    ~
    Les fichiers terminant par "MAP" tracer qui signatures phpMussel devrait et
    ne devrait pas �tre utilis� pour individuelle analyse; Pas toutes les
    signatures sont n�cessairement requises pour chaque unique analyse, ainsi,
    phpMussel utilise cartes fichiers des signatures afin d'acc�l�rer le
    processus d'analyse (un processus qui, autrement, serait extr�mement lent
    et fastidieux).
    ~
    Signature fichiers marqu� avec "_regex" contenir signatures qui
    utilisent regular expression mod�le v�rification (regex).
    ~
    Signature fichiers marqu� avec "_standard" contenir signatures qui
    n'utilisent toute sp�cifique forme de mod�le v�rification.
    ~
    Signature fichiers non marqu�s avec "_regex" ou "_standard" seront aussi
    l'un ou l'autre (mais pas deux); R�f�rer � la Signature Format section de
    ce README fichier pour la documentation et les sp�cifiques d�tails.
    ~
    Signature fichiers marqu� avec "_clamav" contient signatures enti�rement
    bas�e du ClamAV base de donn�es (GNU/GPL).
    ~
    Signature fichiers marqu� avec "_custom", par d�faut, ne contiennent pas
    de signatures; Ces fichiers existent � donner vous un place pour placer
    vos propres personnalis�es signatures, si vous cr�ez une partie de votre
    propre.
    ~
    Signature fichiers marqu� avec "_mussel" contenir signatures qui ne sont
    pas sp�cifiquement provenant par ClamAV, signatures qui, en g�n�ral, je
    d�velopp� par moi-m�me et/ou bas� sur informations recueillies de diverses
    sources.
    ~

                                     ~ ~ ~


 6. CONFIGURATION OPTIONS

 Ce qui suit est une liste de variables trouv� dans le "phpmussel.ini"
 configuration fichier de phpMussel, avec une description de leur objet et leur
 fonction.

 "general" (Cat�gorie)
 - Configuration g�n�rale pour phpMussel.
    "script_password"
    - Par commodit�, phpMussel permettra certaines fonctions (inclus la
      capacit� de r�actualiser phpMussel sur la vol�e) pour �tre d�clench�
      manuellement via POST, GET et QUERY. Toutefois, par mesure de s�curit�,
      pour ce faire, phpMussel s'attend � un mot de passe pour �tre inclus
      dans la commande, � assurer que c'est vous, et pas quelqu'un d'autre,
      attenter de d�clencher manuellement ces fonctions. Fixer script_password
      � le mot de passe que vous souhaitez d'utiliser. Si aucun mot de passe
      est fix�, d�clenchement manuel sera d�sactiv� par d�faut. Utiliser
      quelque chose que vous souvenez, mais qui est difficile � deviner.
      * N'a pas d'influence en mode CLI.
    "logs_password"
    - La m�me comme script_password, mais par l'affichage du contenu de
      scan_log et scan_kills. Pour avoir distincts mots de passe peut �tre
      utile si vous voulez donner � quelqu'un autre acc�s � un ensemble de
      fonctions mais pas l'autre.
      * N'a pas d'influence en CLI mode.
    "cleanup"
    - D�ensemble variables du script et cache apr�s l'ex�cution. Si vous
      n'utilisez pas le script au-del� l'initiale analyse du t�l�chargements,
      devrait ensemble � oui � minimiser l'utilisation de la m�moire. Si vous
      utilisez le script � des fins au-del� l'initiale analyse du
      t�l�chargements, devrait ensemble � non, pour �viter recharger
      inutilement dupliqu� donn�es dans la m�moire. Dans la g�n�rale pratique,
      il devrait probablement �tre ensembl� sur oui, mais, si vous faites cela,
      vous ne serez pas �tre capable d'utiliser le script pour tout chose autre
      que la analyse de fichiers t�l�chargements.
      * N'a pas d'influence en CLI mode.
    "scan_log"
    - Nom du fichier � enregistrer tous les r�sultats d'analyse �. Sp�cifiez
      un nom de fichier, ou laisser vide � d�sactiver.
    "scan_kills"
    - Nom du fichier � enregistrer tous les r�sultats de bloqu� ou tu�
      t�l�chargements �. Sp�cifiez un nom de fichier, ou laisser vide �
      d�sactiver.
    "ipaddr"
    - O� trouver l'IP adresse du connexion demande? (Utile pour services tels
      que Cloudflare et les go�ts) Par D�faut = REMOTE_ADDR
      AVERTISSEMENT: Ne pas changer si vous ne sais pas ce que vous faites!
    "forbid_on_block"
    - Devrait phpMussel envoyer 403 t�tes avec le fichier t�l�chargement bloqu�
      message, ou rester avec l'habitude 200 bien (200 OK)?
      0 = Non (200) [D�faut], 1 = Oui (403).
    "delete_on_sight"
    - Mise en cette option sera instruire le script � tenter imm�diatement
      supprimer tout fichiers elle constate au cours de son analyse
      correspondant � des crit�res de d�tection, que ce soit via des signatures
      ou autrement. Fichiers jug�es "propre" ne seront pas touch�s. Dans le cas
      des archives, l'ensemble d'archive sera supprim� (ind�pendamment de si le
      incrimin� fichier est que l'un de plusieurs fichiers contenus dans
      l'archive). Pour le cas d'analyse de fichiers t�l�chargement,
      g�n�ralement, il n'est pas n�cessaire d'activer cette option sur, parce
      g�n�ralement, php faire purger automatiquement les contenus de son cache
      lorsque l'ex�cution est termin�e, ce qui signifie que il va g�n�ralement
      supprimer tous les fichiers t�l�charg�s � travers elle au serveur sauf
      qu'ils ont d�m�nag�, copi� ou supprim� d�j�. L'option est ajout�e ici
      comme une suppl�mentaire mesure de s�curit� pour le suppl�mentaire
      parano�aque et pour ceux dont copies de php peut pas toujours se
      comporter de la mani�re attendu.
      0 - Apr�s l'analyse, laissez le fichier tel quel [D�faut],
      1 - Apr�s l'analyse, si pas propre, supprimer imm�diatement.
    "lang"
    - Sp�cifier la d�faut langue pour phpMussel.
    "quarantine_key"
    - phpMussel est capable de mettre en quarantaine le marqu� fichier
      t�l�chargement tentatives en isolement au sein de la vo�te de phpMussel,
      si cela est quelque chose que vous voulez qu'il fasse. L'utilisateurs de
      phpMussel qui souhaitent simplement de prot�ger leurs sites ou
      environnement d'h�bergement sans avoir un profond�ment int�r�t dans
      d'analyse de quelconque marqu� fichier t�l�chargement tentatives devrait
      laisser cette fonctionnalit� d�sactiv�e, mais tous les utilisateurs
      int�ress�s dans d'analyse plus approfondie de tent� fichier
      t�l�chargements pour la recherche des logiciels malveillants ou pour des
      choses semblables devraient permettre cette fonctionnalit�. La
      quarantaine de marqu� fichier t�l�chargement tentatives peut parfois
      aider �galement dans le d�bogage des faux positifs, si cela est quelque
      chose qui se produit fr�quemment pour vous. Pour d�sactiver la
      fonctionnalit� de quarantaine, il suffit de laisser la directive
      "quarantine_key" vide, ou effacer le contenu de cette directive si elle
      est pas d�j� vide. Pour activer la fonctionnalit� de quarantaine, entrer
      une valeur dans la directive. Le "quarantine_key" est une �l�ment
      important de la s�curit� de la fonctionnalit� de quarantaine requis en
      tant que moyen de pr�vention de la fonctionnalit� de quarantaine d'�tre
      exploit�s par des attaquants potentiels en tant que moyen de pr�vention
      toute potentielle ex�cution de donn�es stock�es dans la quarantaine. Le
      "quarantine_key" devrait �tre trait� de la m�me mani�re que vos mots de
      passe: Le plus sera le mieux, et conservez-le bien. Pour un meilleur
      effet, utiliser en conjonction avec "delete_on_sight".
    "quarantine_max_filesize"
    - La maximum autoris�e taille de fichiers mis en quarantaine. Fichiers
      au-dessus de cette valeur ne sera pas plac� en quarantaine. Cette
      directive est un important moyen de rendre plus difficile pour des
      agresseurs potentiels d'inonder votre quarantaine avec des non d�sir�es
      donn�es ce qui pourrait causer l'emballement d'utilisation des donn�es
      sur votre service d'h�bergement. La valeur est en Ko.
      D�faut =2048 =2048Ko =2Mo.
    "quarantine_max_usage"
    - La maximale autoris�e utilisation de la m�moire pour la quarantaine. Si
      la totale utilis�e m�moire par la quarantaine atteint cette valeur, les
      anciens fichiers en quarantaine seront supprim�s jusqu'� ce que la totale
      m�moire utilis�e n'atteint pas cette valeur. Cette directive est un
      important moyen de rendre plus difficile pour des agresseurs potentiels
      d'inonder votre quarantaine avec des non d�sir�es donn�es ce qui pourrait
      causer l'emballement d'utilisation des donn�es sur votre service
      d'h�bergement. La valeur est en Ko. D�faut =65536 =65536Ko =64Mo.
    "honeypot_mode"
    - Lorsque le honeypot mode est activ�, phpMussel va tenter de mettre en
      quarantaine tous les fichier t�l�chargements ce qu'il rencontre,
      ind�pendamment de si oui ou non le fichier en cours de t�l�chargement
      correspond � signature inclus, et aucune r�elle analyse de ces fichier
      t�l�chargements tentatives va arriver. Cette fonctionnalit� devrait �tre
      utile pour ceux qui souhaitent utiliser phpMussel pour des fins de
      logiciels malveillants ou virus recherche, mais il pas n'est recommand�
      d'activer cette fonctionnalit� si l'utilisation pr�vue de phpMussel par
      l'utilisateur est l'analyse de fichier t�l�chargements comme la norme, ni
      est-il recommand� d'utiliser la honeypot fonctionnalit� pour fins autres
      que de honeypotting. Par d�faut, cette option est d�sactiv�e.
      0 = D�sactiv� [D�faut], 1 = Activ�.
 "signatures" (Cat�gorie)
 - Configuration pour les signatures.
   %%%_clamav = ClamAV signatures (mains et daily).
   %%%_custom = Vos personnalis�s signatures (si vous avez �crit tout).
   %%%_mussel = phpMussel signatures incluses dans votre courant ensemble des
                signatures qui ne sont pas de ClamAV.
   - V�rifier contre MD5 signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - V�rifier contre g�n�ral signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - V�rifier contre normalis� ASCII signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - V�rifier contre normalis� HTML signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - V�rifier PE (Portable Ex�cutable) fichiers (EXE, DLL, etc) contre PE
     Sectional signatures au cours de analyse? 0 = Non, 1 = Oui [D�faut].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - V�rifier PE (Portable Ex�cutable) fichiers (EXE, DLL, etc) contre PE
     signatures au cours de analyse? 0 = Non, 1 = Oui [D�faut].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - V�rifier ELF fichiers contre ELF signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - V�rifier Mach-O fichiers (OSX, etc) contre Mach-O signatures au cours de
     analyse? 0 = Non, 1 = Oui [D�faut].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - V�rifier graphiques fichiers contre graphiques bas� signatures au cours de
     analyse? 0 = Non, 1 = Oui [D�faut].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - V�rifier archives contenu contre archive m�tadonn�es signatures au cours
     de analyse? 0 = Non, 1 = Oui [D�faut].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - V�rifier OLE objets contre OLE signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - V�rifier les noms de fichiers contre signatures bas� sur les noms de
     fichiers au cours de analyse? 0 = Non, 1 = Oui [D�faut].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Autoriser analyse avec phpMussel_mail()? 0 = Non, 1 = Oui [D�faut].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Activer fichier sp�cifique blanche liste? 0 = Non, 1 = Oui [D�faut].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - V�rifier XML/XDP morceaux contre XML/XDP morceaux signatures au cours de
     analyse? 0 = Non, 1 = Oui [D�faut].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - V�rifier contre Complexe �tendu signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - V�rifier contre PDF signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - V�rifier contre Shockwave signatures au cours de analyse?
     0 = Non, 1 = Oui [D�faut].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Signature correspondance longueur limiter options. Seulement modifier si
     vous savez ce que vous faites. SD = Standard signatures. RX = PCRE (Perl
     Compatibles R�guli�res Expressions, ou "Regex") signatures. FN = Nom de
     fichier signatures. Si vous remarquez php s'�craser quand phpMussel
     tentatives d'analyse, tenter � r�duire ces "max" valeurs. Si possible et
     pratique, laissez-moi savoir quand cela se produit et les r�sultats de ce
     que vous essayez.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Devrait phpMussel signaler lorsque les signatures fichiers sont manquants
     ou endommag�s? Si fail_silently est d�sactiv�, manquants et corrompus
     fichiers seront signal� sur analyse, et if fail_silently est activ�,
     manquants et corrompus fichiers seront ignor�s, avec l'analyse signal�s
     pour ceux fichiers qu'il n'y a pas de probl�mes. Cela devrait g�n�ralement
     �tre laiss� seul sauf si vous rencontrez accidents ou similaires
     probl�mes. 0 = D�sactiv�, 1 = Activ� [D�faut].
     "fail_silently"
 "files" (Cat�gorie)
 - G�n�rale configuration pour gestion des fichiers.
   "max_uploads"
   - Maximum admissible nombre de fichiers pour analyse lorsque l'analyse de
     fichier t�l�chargements avant d'abandonner l'analyse et informer
     l'utilisateur qu'ils sont t�l�chargement trop � la fois! Fournit
     protection contre une th�orique attaque par lequel un attaquant tente �
     DDoS votre syst�me ou CMS par surchargeant phpMussel � ralentir le
     processus de php � une halte. Recommand�: 10. Vous pouvez d�sirer
     d'augmenter ou diminuer ce nombre d�pendamment de la vitesse de votre
     hardware. Notez que ce nombre ne tient pas compte pour ou inclure le
     contenus des archives.
   "filesize_limit"
   - Limite de taille de fichier en Ko. 65536 = 64Mo [D�faut], 0 = Pas limite
     (toujours en liste grise), tout (positif) valeur num�rique accept�e. Cela
     peut �tre utile lorsque votre configuration de PHP limite la quantit� de
     m�moire qu'un processus peut contenir ou si votre configuration de PHP
     limite la taille du fichier t�l�chargements.
   "filesize_response"
   - Que faire avec des fichiers qui d�passent la taille de fichier limite (si
     existant). 0 - �num�rer Blanche, 1 - �num�rer Noire [D�faut].
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - Si votre syst�me seulement permettre particuliers types de fichiers �
     t�l�charg�, ou si votre syst�me nie explicitement particuliers types de
     fichiers, sp�cifiant les types de fichiers dans listes blanches, listes
     noires et listes gris peut augmenter la vitesse � laquelle l'analyse est
     effectu�e en permettant le script � sauter particuliers types de fichiers.
     Format est CSV (virgule s�par�es valeurs). Si vous souhaitez analyse tout,
     plut�t que de liste blanche, liste noire ou liste gris, laisser les
     variable(/s) blanc; Il va d�sactiver liste blanche/noire/gris. L'ordre
     logique de l'application est:
     - Si le type de fichier est list� blanche, n'analyser pas ni bloquer pas
       le fichier, et ne v�rifie pas le fichier contre la liste noire ou la
       liste grise.
     - Si le type de fichier est list� noire, n'analyser pas le fichier mais
       bloquer de toute fa�on, et ne v�rifie pas le fichier contre la liste
       grise.
     - Si la liste grise est vide ou si la liste grise n'est vide pas et le
       type de fichier est list� grise, analyser le fichier comme d'habitude et
       d�terminer si de bloquer bas�s des r�sultats de l'analyse, mais si la
       liste grise n'est vide pas et le type de fichier n'est list� grise pas,
       traiter le fichier comme list� noire, donc n'analyse pas mais bloque de
       toute fa�on.
   "check_archives"
   - Essayez v�rifier le contenu des archives?
     0 - Non (ne pas v�rifier), 1 - Oui (v�rifier) [D�faut].
     * Actuellement, seulement l'examen de BZ, GZ, LZF et ZIP fichiers est
       support� (l'examen RAR, CAB, 7z etc actuellement pas support�).
     * Ce n'est pas � toute �preuve! Bien que je recommande fortement d'avoir
       ce reste activ�e, je ne peux pas garantir il va toujours trouver tout.
     * Aussi �tre conscient que l'examen d'archives actuellement n'est pas
       r�cursif pour ZIPs.
   "filesize_archives"
   - �tendre taille du fichier liste noire/blanche param�tres � le contenu des
     archives? 0 - Non (�num�rer grise tout), 1 - Oui [D�faut].
   "filetype_archives"
   - �tendre type de fichier liste noire/blanche param�tres � le contenu des
     archives? 0 - Non (�num�rer grise tout), 1 - Oui [D�faut].
   "max_recursion"
   - Maximum r�cursivit� profondeur limite pour archives. D�faut = 10.
 "attack_specific" (Cat�gorie)
 - Configuration pour les sp�cifique attaque d�tections (pas bas� sur CVDs).
   * Cam�l�on Attaque D�tection: 0 = D�sactiv�, 1 = Activ�.
   "chameleon_from_php"
   - V�rifier pour php t�te dans les fichiers qui sont ni php fichiers ni
     reconnue comme archives.
   "chameleon_from_exe"
   - V�rifier pour ex�cutable t�tes dans les fichiers qui sont ni ex�cutable
     fichiers ni reconnue comme archives et pour ex�cutables dont t�tes sont
     incorrects.
   "chameleon_to_archive"
   - V�rifier pour archives dont t�tes sont incorrects (Support�: BZ, GZ, RAR,
     ZIP, RAR, GZ).
   "chameleon_to_doc"
   - V�rifier pour office documents dont t�tes sont incorrects (Support�: DOC,
     DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - V�rifier pour images dont t�tes sont incorrects (Support�: BMP, DIB, PNG,
     GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - V�rifier pour PDF fichiers dont t�tes sont incorrects.
   "archive_file_extensions" et "archive_file_extensions_wc"
   - Les extensions de reconnus archive fichiers (format est CSV; devraient
     ajouter ou supprimer seulement quand probl�mes surviennent; supprimer
     inutilement peut entra�ner des faux positifs � para�tre pour archive
     fichiers, tandis que ajoutant inutilement sera essentiellement liste
     blanche ce que vous ajoutez � partir de l'attaque sp�cifique d�tection;
     modifier avec prudence; aussi noter que cela n'a aucun effet sur ce
     archives peut et ne peut pas �tre analys� au niveau du contenu). La liste,
     comme en cas de d�faut, �num�re les formats plus couramment utilis� dans
     la majorit� des syst�mes et CMS, mais volontairement pas n�cessairement
     compl�te.
   "general_commands"
   - V�rifier de fichiers pour g�n�rales commandes comme eval(), exec() et
     include()? 0 - Non (pas v�rifier) [D�faut], 1 - Oui (v�rifier).
     D�finir comme 0 (Non) si vous avez l'intention � t�l�charger de la suivant
     � votre syst�me ou CMS via votre navigateur: php, JavaScript, HTML,
     python, perl fichiers etc. D�finir comme 1 (Oui) si vous n'avez pas de
     suppl�mentaire protections sur votre syst�me et n'ont pas l'intention de
     t�l�charger ces fichiers. Si vous utilisez une suppl�mentaire s�curit� en
     conjonction avec phpMussel comme ZB Block, il n'est pas n�cessaire
     d'activer cette option, parce la plupart de que phpMussel va chercher pour
     (dans le contexte de cette option) sont des duplications de protections
     qui sont d�j� fournis.
   "block_control_characters"
   - Bloquer tous les fichiers contenant des contr�le caract�res (autre que les
     sauts de ligne)? ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) Si vous �tes
     -seulement- t�l�charger de brut texte fichiers, puis vous pouvez activer
     cette option � fournir une suppl�mentaire protection � votre syst�me.
     Mais, si vous t�l�charger quelque chose plus que brut texte, l'activation
     de cette peut cr�er faux positifs.
     0 - Ne pas bloquer [D�faut], 1 - Bloquer.
   "corrupted_exe"
   - Corrompus fichiers et des erreurs d'analyse.
     0 = Ignorer, 1 = Bloquer [D�faut]. D�tecter et bloquer les potentiellement
     corrompus PE (Portable Executable) fichiers? Souvent (mais pas toujours),
     lorsque certains aspects d'un PE fichier sont corrompus ou ne peut pas
     �tre analys�e correctement, il peut �tre le signe d'une virale infection.
     Les processus utilis�s par la plupart des anti-virus programmes pour
     d�tecter les virus dans PE fichiers requ�rir l'analyse de ces fichiers par
     certaines m�thodes, de ce que, si le programmeur d'un virus est conscient
     de, seront sp�cifiquement tenter d'emp�cher, en vue de permettre leur
     virus n'�tre pas d�tect�e.
   "decode_threshold"
   - Facultatif limitation ou seuil � la longueur de brutes donn�es dans
     laquelle commandes des d�codages doivent �tre d�tect�s (dans le cas o� il
     ya remarquable performance probl�mes au cours de l'analyse). La valeur est
     un entier repr�sentant la tailles des fichiers en Ko.
     D�faut = 512 (512Ko). Z�ro ou nulle valeur d�sactive le seuil (supprimant
     toute restriction bas� sur la taille du fichier).
   "scannable_threshold"
   - Facultatif limitation ou seuil � la longueur de brutes donn�es dans
     laquelle phpMussel est autoris� � lire et � analyser (dans le cas o� il ya
     remarquable performance probl�mes au cours de l'analyse). La valeur est un
     entier repr�sentant la tailles des fichiers en Ko. D�faut = 32768 (32Mo).
     Z�ro ou nulle valeur d�sactive le seuil. En g�n�ral, cette valeur ne doit
     pas �tre moins que la moyenne tailles des fichiers des t�l�chargements que
     vous voulez et s'attendent � recevoir de votre serveur ou website, ne
     devrait pas �tre plus que la filesize_limit directive, et ne devrait pas
     �tre plus que d'un cinqui�me de l'allocation de totale m�moire autoris�e �
     PHP via le php.ini configuration fichier. Cette directive existe pour
     tenter d'emp�cher phpMussel d'utiliser trop de m�moire (ce qui
     l'emp�cherait d'�tre capable d'analyse fichiers dessus d'une certaine
     taille avec succ�s).
 "compatibility" (Cat�gorie)
 - Compatibilit� directives pour phpMussel.
   "ignore_upload_errors"
   - Cette directive doit g�n�ralement �tre D�SACTIV� sauf si cela est
     n�cessaire pour la correcte fonctionnalit� de phpMussel sur votre
     sp�cifique syst�me. Normalement, lorsque D�SACTIV�, lorsque phpMussel
     d�tecte la pr�sence d'�l�ments dans le $_FILES() tableau, il va tenter de
     lancer une analyse du fichiers que ces �l�ments repr�sentent, et, si ces
     �l�ments sont vide, phpMussel retourne un message d'erreur. Ce
     comportement est normal pour phpMussel. Mais, pour certains CMS, vides
     �l�ments dans $_FILES peuvent survenir � la suite du naturel comportement
     de ces CMS, ou erreurs peuvent �tre signal�s quand il ne sont pas tout,
     dans ce cas, le normal comportement pour phpMussel seront interf�rer avec
     le normal comportement de ces CMS. Si telle une situation se produit pour
     vous, ACTIVATION de cette option sera instruire phpMussel ne pas � tenter
     de lancer d'analyses pour ces vides �l�ments, ignorer quand il est reconnu
     et ne pas � retourner tout de connexes messages d'erreur, permettant ainsi
     la continuation de la page demande. 0 - D�SACTIV�, 1 - ACTIV�.
   "only_allow_images"
   - Si vous seulement attendre ou vouloir d'autoriser images � �tre t�l�charg�
     sur votre syst�me ou CMS, et si vous absolument n'avez pas besoin tous les
     fichiers autres que les images � �tre t�l�charg� sur votre syst�me ou CMS,
     cette directive devrait �tre ACTIV�, mais devrait autrement �tre
     D�SACTIV�. Si cette directive est ACTIV�, il va instruire phpMussel �
     bloquer indistinctement tous t�l�chargements identifi� comme non image
     fichiers, sans analyser. Cela peut r�duire le temps de travail et
     l'utilisation de la m�moire pour les tentativ� t�l�chargements de non
     image fichiers. 0 - D�SACTIV�, 1 - ACTIV�.
 "heuristic" (Cat�gorie)
 - Heuristiques directives pour phpMussel.
   "threshold"
   - Il ya certaines signatures des phpMussel qui sont destin�s � identifier
     des suspectes et potentiellement malveillants qualit�s des fichiers en
     cours de t�l�chargement sans en eux-m�mes identifier les fichiers en cours
     de t�l�chargement sp�cifiquement comme �tant malveillants. Cette
     "threshold" (seuil) valeur raconte � phpMussel ce que le total maximum
     poids des suspectes et potentiellement malveillants qualit�s des fichiers
     en cours de t�l�chargement pour ce qui est admissible avant que ces
     fichiers doivent �tre signal�es comme malveillant. La d�finition du poids
     dans ce contexte est le nombre total de suspectes et potentiellement
     malveillants qualit�s identifi�. Par d�faut, cette valeur sera fix�e � 3.
     Une valeur inf�rieur va r�sulter g�n�ralement avec une fr�quence sup�rieur
     de faux positifs mais une nombre sup�rieur de fichiers signal� comme
     malveillant, tandis que une valeur inf�rieur va r�sulter g�n�ralement avec
     une fr�quence inf�rieur de faux positifs mais un nombre inf�rieur de
     fichiers signal� comme malveillant. Il est g�n�ralement pr�f�rable de
     laisser cette valeur � sa valeur d�faut, sauf si vous rencontrez des
     probl�mes qui sont li�s � elle.

                                     ~ ~ ~


 7. SIGNATURE FORMAT

 = NOM DE FICHIER SIGNATURES =
   Toutes les nom de fichier signatures suivez le format:
    NOM:FNRX
   O� NOM est le nom � citer pour la signature et FNRX est l'expression
   rationnelle pour faire correspondre les (non cod�) noms de fichiers.

 = MD5 SIGNATURES =
   Toutes les MD5 signatures suivez le format:
    HASH:TAILLE:NOM
   O� HASH est le MD5 hash d'un ensemble du fichier, TAILLE est la totale
   taille du fichier et NOM est le nom � citer pour la signature.

 = ARCHIVE M�TADONN�ES SIGNATURES =
   Toutes les archive m�tadonn�es signatures suivez le format:
    NOM:TAILLE:CRC32
   O� NOM est le nom � citer pour la signature, TAILLE est la totale taille
   (non compress�) d'un fichier contenues dans l'archive et CRC32 est la CRC32
   contr�le somme of de ce fichier contenu.

 = PE SECTIONAL SIGNATURES =
   Toutes les PE Sectional signatures suivez le format:
    TAILLE:HASH:NOM
   O� HASH est le MD5 hash d'un section du PE fichier, TAILLE est la totale
   taille de cet section et NOM est le nom � citer pour la signature.

 = BLANCHE LISTE SIGNATURES =
   Toutes les blanche liste signatures suivez le format:
    HASH:TAILLE:TYPE
   O� HASH est le MD5 hash d'un ensemble du fichier, TAILLE est la totale
   taille du fichier et TYPE est le type de signatures le list� blanche fichier
   est d'�tre immunitaire contre.

 = COMPLEXES �TENDUES SIGNATURES =
   Complexes �tendues signatures sont assez diff�rentes pour les autres types
   de signatures possible avec phpMussel, dans que ce qu'ils v�rifient contre
   est sp�cifi� par les signatures elles-m�mes et ils peuvent v�rifier contre
   plusieurs crit�res. Les crit�res sont d�limit�es par ";" et le type et les
   donn�es de chacun crit�res est d�limit�e par ":" comme ainsi le format de
   ces signatures tendances � semble un peu comme:
    $variable1:CERTAINSDONN�ES;$variable2:CERTAINSDONN�ES;SignatureNom

 = TOUT LE RESTE =
   Toutes les autre signatures suivez le format:
    NOM:HEX:FROM:TO
   O� NOM est le nom � citer pour la signature et HEX est un hexad�cimal cod�
   segment du fichier destin� � �tre identifi� par la signature donn�e. FROM et
   TO sont optionnel param�tres, indication de laquelle et � laquelle les
   positions dans les source donn�es pour v�rifier contre (non support� par la
   mail fonction).

 = REGEX =
   Toute forme de regex comprise et pr�par� correctement par php devrait aussi
   �tre correctement compris et pr�par� par phpMussel et ses signatures. Mais,
   je vous sugg�re de prendre une extr�me prudence lors de l'�criture de
   nouvelles regex bas� signatures, parce, si vous n'�tes pas enti�rement s�r
   de ce que vous faites, il peut y avoir tr�s irr�guliers et/ou inattendus
   r�sultats. Jetez un oeil � la phpMussel source code si vous n'�tes pas
   enti�rement s�r sur le contexte dans lequel regex d�clarations sont
   analys�s. Aussi, rappeler toutes les d�clarations (� l'exception de nom de
   fichier, archive m�tadonn�es et MD5 d�clarations) doit �tre de cod� de
   hexad�cimale (� l'exception de d�claration syntaxe, bien s�r)!

 = O� METTRE DES PERSONNALIS�ES SIGNATURES? =
   Seulement mettre des personnalis�es signatures dans les fichiers pr�vu pour
   personnalis�es signatures. Ces fichiers devrait contenir "_custom" dans leur
   noms. Vous devrait aussi �viter modifier les d�faut signature fichiers, sauf
   si vous savez exactement ce que vous faites, parce, en plus d'�tre une bonne
   pratique en g�n�ral et aidant vous � distinguer entre vos signatures et le
   d�faut signatures inclus avec phpMussel, il est bon de tenir � l'�dition
   seuls les fichiers destin�s � l'�dition, parce que l'alt�ration du d�faut
   signature fichiers peut cess� leur fonctionner correctement, en raison des
   "maps" fichiers: Les maps fichiers racontent phpMussel o� dans le signature
   fichiers � chercher pour requis signatures par phpMussel selon lorsque
   requis, et ces maps peut devenir d�synchronis�e avec leur associ� signature
   fichiers si le signature fichiers sont alt�r�. Vous pouvez mettre � peu pr�s
   ce que vous voulez dans vos personnalis�e signatures, aussi longtemps que
   vous suivez la correcte syntaxe. Mais, �tre prudent � tester nouvelles
   signatures pour faux positifs avant si vous avez l'intention � partager ou
   utiliser dans un r�el environnement.

 = SIGNATURE D�TAIL =
   Ce qui suit est un d�tail des types de signatures utilis�es par phpMussel:
   - "Normalis� ASCII Signatures" (ascii_*). V�rifi� contre les contenus de
      chaque fichier non list� blanche et cibl�e pour d'analyse.
   - "Complexes �tendues Signatures" (coex_*). Mixte types des signatures
      correspondant.
   - "ELF Signatures" (elf_*). V�rifi� contre les contenus de chaque fichier
      non list� blanche, cibl�e pour l'analyse et identifi� au ELF format.
   - "Portable Executable Signatures" (exe_*). V�rifi� contre les contenus de
      chaque fichier non list� blanche, cibl�e pour l'analyse et identifi� au
      PE format.
   - "Filename Signatures" (filenames_*). V�rifi� contre les noms de fichiers
      cibl� pour d'analyse.
   - "G�n�rales Signatures" (general_*). V�rifi� contre les contenus de chaque
      fichier non list� blanche et cibl�e pour d'analyse.
   - "Graphics Signatures" (graphics_*). V�rifi� contre les contenus de chaque
      fichier non list� blanche, cibl�e pour l'analyse et identifi� � un connu
      graphique fichier format.
   - "G�n�rales Commandes" (hex_general_commands.csv). V�rifi� contre les
      contenus de chaque fichier non list� blanche et cibl�e pour d'analyse.
   - "Normalis� HTML Signatures" (html_*). V�rifi� contre les contenus de
      chaque fichier de HTML non list� blanche et cibl�e pour d'analyse.
   - "Mach-O Signatures" (macho_*). V�rifi� contre les contenus de chaque
      fichier non list� blanche, cibl�e pour l'analyse et identifi� au Mach-O
      format.
   - "Email Signatures" (mail_*). V�rifi� contre le $corps variable analys�e �
      la phpMussel_mail() fonction, qui est destin� � �tre le corps des e-mails
      ou similaire entit�s (potentiellement messages du forum et etc).
   - "MD5 Signatures" (md5_*). V�rifi� contre le MD5 hash des contenus et
      taille de chaque fichier non list� blanche et cibl�e pour d'analyse.
   - "Archives M�tadonn�es Signatures" (metadata_*). V�rifi� contre le CRC32
      hash et taille de l'initial fichier contenu � l'int�rieur de toute
      archive non list� blanche et cibl�e pour d'analyse.
   - "OLE Signatures" (ole_*). V�rifi� contre les contenus de chaque objet non
      list� blanche et cibl�e pour d'analyse.
   - "PDF Signatures" (pdf_*). V�rifi� contre les contenus de chaque PDF
      fichier non list� blanche.
   - "Portable Executable Sectional Signatures" (pe_*). V�rifi� contre le
      taille et l'MD5 hash des sections de chaque PE fichier non list� blanche,
      cibl�e pour l'analyse et identifi� au PE format.
   - "SWF Signatures" (swf_*). V�rifi� contre les contenus de chaque Shockwave
      fichier non list� blanche.
   - "Blanche Liste Signatures" (whitelist_*). V�rifi� contre le MD5 hash des
      contenus et la taille de chaque fichier cibl�e pour d'analyse. Les
      identifi�s fichiers sera immunitaire d'�tre identifi� par le type de
      signature mentionn� dans leur entr�e de blanche liste.
   - "XML/XDP Morceaux Signatures" (xmlxdp_*). V�rifi� contre de chaque XML/XDP
      morceaux trouv�s dans tout fichier non list� blanche et cibl�e pour
      l'analyse.
   (Noter que ces signatures peut �tre facilement d�sactiv� via phpmussel.ini).

                                     ~ ~ ~


 8. CONNUS PROBL�MES DE COMPATIBILIT�

 PHP et PCRE
 - phpMussel requ�rir PHP et PCRE � signer et � fonctionner correctement. Sans
   PHP, ou sans le PCRE extension de PHP, phpMussel n'ex�cutera pas ou
   fonctionnent correctement. Devrait s'assurer que votre syst�me avoir PHP et
   PCRE install� et disponible avant de votre t�l�chargement et installation de
   phpMussel.

 ANTI-VIRUS LOGICIELS COMPATIBILIT�

 Pour la plupart, phpMussel devrait �tre assez compatible avec plupart du virus
 d�tection logiciels. Cependant, conflictualit�s ont �t� signal�s par un nombre
 d'utilisateurs dans le pass�. Cette information ci-dessous est VirusTotal.com,
 et il d�crit un certain nombre de faux positifs signal� par divers anti-virus
 programmes contre phpMussel. Bien que cette information ne constitue pas une
 absolue garantie de si oui ou non vous rencontrerez des probl�mes de
 compatibilit� entre phpMussel et votre anti-virus logiciel, si votre logiciel
 anti-virus est not� comme signalant contre phpMussel, vous devriez envisager
 d�sactivation avant � travailler avec phpMussel ou devrait envisager d'autres
 options soit votre logiciel anti-virus ou phpMussel.

 Cette information a �t� r�actualis� le 1 Mai 2015 et est courant pour toutes
 les phpMussel parutions des deux plus r�centes mineures versions (v0.5-v0.6)
 au moment de la r�daction cette.

 Ad-Aware                Pas probl�mes connus
 Agnitum                 Pas probl�mes connus
 AhnLab-V3               Pas probl�mes connus
 AntiVir                 Pas probl�mes connus
 Antiy-AVL               Pas probl�mes connus
 Avast                !  Rapports "JS:ScriptSH-inf [Trj]"
 AVG                     Pas probl�mes connus
 Baidu-International     Pas probl�mes connus
 BitDefender             Pas probl�mes connus
 Bkav                    Pas probl�mes connus
 ByteHero                Pas probl�mes connus
 CAT-QuickHeal           Pas probl�mes connus
 ClamAV                  Pas probl�mes connus
 CMC                     Pas probl�mes connus
 Commtouch               Pas probl�mes connus
 Comodo                  Pas probl�mes connus
 DrWeb                   Pas probl�mes connus
 Emsisoft                Pas probl�mes connus
 ESET-NOD32              Pas probl�mes connus
 F-Prot                  Pas probl�mes connus
 F-Secure                Pas probl�mes connus
 Fortinet                Pas probl�mes connus
 GData                   Pas probl�mes connus
 Ikarus                  Pas probl�mes connus
 Jiangmin                Pas probl�mes connus
 K7AntiVirus             Pas probl�mes connus
 K7GW                    Pas probl�mes connus
 Kaspersky               Pas probl�mes connus
 Kingsoft                Pas probl�mes connus
 Malwarebytes            Pas probl�mes connus
 McAfee               !  Rapports "New Script.c"
 McAfee-GW-Edition    !  Rapports "New Script.c"
 Microsoft               Pas probl�mes connus
 MicroWorld-eScan        Pas probl�mes connus
 NANO-Antivirus          Pas probl�mes connus
 Norman               !  Rapports "Kryptik.BQS"
 nProtect                Pas probl�mes connus
 Panda                   Pas probl�mes connus
 Qihoo-360               Pas probl�mes connus
 Rising                  Pas probl�mes connus
 Sophos                  Pas probl�mes connus
 SUPERAntiSpyware        Pas probl�mes connus
 Symantec             !  Rapports "WS.Reputation.1"
 TheHacker               Pas probl�mes connus
 TotalDefense            Pas probl�mes connus
 TrendMicro              Pas probl�mes connus
 TrendMicro-HouseCall    Pas probl�mes connus
 VBA32                   Pas probl�mes connus
 VIPRE                   Pas probl�mes connus
 ViRobot                 Pas probl�mes connus


                                     ~ ~ ~


Derni�re R�actualis�: 24 Mai 2015 (2015.05.24).
EOF
# Voice_Assistant_TARS ![Tars_icon](https://github.com/Hypocrate-code/Voice_Assistant_TARS/assets/112576942/cdff1119-821a-45f9-8641-108220bcec4b)  
Notre participation, avec mes 2 deux camarades de classe [Mathilde Jeaunaux](https://www.instagram.com/mathilde_jnx/) et [Olivier Serra](https://www.instagram.com/olivier_sra/) au concours national [Les trophées NSI](https://trophees-nsi.fr/).  
Il s'agit d'un assistant vocal nommé Tars (en référence au robot assistant l'équipe spatiale dans le film Interstellar) installable dès maintenant sur un Raspberry Pi 4, dont la personnalité (humour, sarcasme, etc...) ainsi que la voix sont customisables par l'utilisateur. Il a notamment pour but d'être plus éthique que les assistants vocaux proposés par les GAFAM, accusés à mainte reprise de surveillance audio par leurs utilisateurs.   

Vidéo de présentation : [Trophées NSI : TARS, notre assitant vocal personnalisable et éthique](https://tube-sciences-technologies.apps.education.fr/w/iYhgGHpcaSYZz9as2D67sj)  
* [Exemples de fonctionnalités](#fonctionnalités)
* [Axes d'amélioration](#amélioration-axes)
* [Comment installer Tars](#installation)
* [Lancer Tars pour la première fois](#premier-lancement)
* [Ajouter vos propres commandes vocales](#vocal-commands)  
## <a id="fonctionnalités">Exemples de fonctionnalités :</a>
* Panneau de configuration pour modifier ses caractéristiques
* Traduction de mots et phrases dans d'autres langues
* Répondre n'importe quelle question de culture générale
* Donner une recette de cuisine et ses ingrédients
* Trouver des synonymes
* Donner l'heure
* Et bien d'autres !
## <a id="amélioration-axes">Axes d'amélioration :</a>
* La meilleure amélioration qui pourrait être réalisée serait la mise en place de notre propre modèle de machine learning, pour le wakeword, plutôt que de dépendre de Porcupine sur ce point là 
* Traduire Tars, aussi bien son interface, que son wakeword et la langue avec laquelle il nous répond, serait un bon ajout afin d'ouvrir ce projet au monde extérieur à la France 
* Ajouter la possibilité de donner la météo à un endroit précis, après configuration via son site Web 
## <a id="installation">Comment installer Tars :</a>  
Pour installer Tars, deux choix s'offrent à vous :
* Installer la dernière version de Tars pour une utilisation rapide
* Installer le projet pour pouvoir ajouter vos propres commandes vocales
### Installation directe
Une fois muni de votre Raspberry Pi et d'une carte SD vierge, rendez vous sur la section ["release"](https://github.com/Hypocrate-code/Voice_Assistant_Tars/releases), et téléchargez la version la plus récente de Tars. Ensuite, à l'aide du logiciel [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/), sélectionnez le fichier de Tars, la bonne carte SD, et cliquez sur "Write". Une fois le processus terminé, il ne vous reste plus qu'à insérer la carte SD dans votre Raspberry Pi, et vous en tenir au déroulement du [premier lancement](#premier-lancement).
### Installation du projet lui-même
Il vous faudra sur votre machine Python ainsi que pip pour installer les différentes dépendances. Vous n'avez qu'à entrer les commandes suivantes dans votre terminal.  

Pour télécharger le projet :  
`git clone https://github.com/Hypocrate-code/Voice_Assistant_TARS.git`  

Puis pour installer toutes les dépendances nécessaires, dans le dossier /sources :  
`pip install -r requirements.txt`  
## <a id="premier-lancement">Lancer Tars pour la première fois :</a>
Avant de lancer Tars pour la première fois, il faut suivre un protocole simple en quelques étapes :
1. Branchez Tars à votre réseau via un cable ethernet. Il lui faut une connexion internet pour que vous puissiez accéder à son panneau de configuration.
2. Allumez et branchez une enceinte à Tars. C'est via cette sortie son, qu'une fois démaré, il vous donnera les instructions à suivre.
3. Branchez un microphone USB (optionnel au démarage) à votre Raspberry Pi pour que Tars puisse par la suite vous écouter
4. Alimentez Tars en électricité via un cable USB Type-C, avec une puissance suffisante pour que votre Raspberry Pi démarre.
5. Après quelques petites minutes (une ou deux), vous devriez entendre un son retentir : Tars démarre. Il ne vous reste ensuite plus qu'à suivre ses instructions.
## <a id="vocal-commands">Ajouter vos propres commandes vocales :</a>
Vous pouvez en effet ajouter vos propres commandes vocales très simplement, il ne vous sera nécessaire que quelques connaissances en python pour développer la fonctionnalité que vous souhaitez.
Pour ce faire, il vous faudra vous rendre dans le fichier [tars_connected/functions_assignement.json](https://github.com/Hypocrate-code/Voice_Assistant_TARS/blob/main/sources/tars_connected/functions_assignement.json), où vous pouvez en premier lieu ajouter une clé au dictionnaire JSON, le nom de votre fonction (ce n'a strictement aucune importance), associée à un dictionnaire contenant lui même deux clés :
* "patterns", dont la valeur doit être une liste contenant tous les mots clé ou phrases qui seront détectés pour éxecuter votre fonction, sur le même schéma que les autres fonctions présentes.
* "name of function", dont la valeur est le nom de votre fonction Python que vous coderez.

Une fois fait, il ne vous reste plus qu'à coder votre fonction dans le fichier [tars_connected/tars_functions.py](https://github.com/Hypocrate-code/Voice_Assistant_TARS/blob/main/sources/tars_connected/tars_functions.py), ayant pour nom obligatoirement la valeur de la clé "name of function" précédemment citée. Cette fonction prendra pour argument la file d'attente des différentes phrases que Tars dit, sur laquelle vous pouvez utiliser la méthode .say(texte_à_dire, priorité) pour lui ajouter une phrase. Le paramètre priorité est un nombre entre 1 et 2, 1 plaçant la phrase avant les suivantes, et 2 la plaçant à la phrase.

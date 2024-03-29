# Voice_Assistant_TARS
Notre participation, avec mes 2 deux camarades de classe [Mathilde Jeaunaux](https://www.instagram.com/mathilde_jnx/) et [Olivier Serra](https://www.instagram.com/olivier_sra/) au concours national [Les trophées NSI](https://trophees-nsi.fr/).  
Il s'agit d'un assistant vocal nommé Tars (en référence au robot assistant l'équipe spatiale dans le film Interstellar) installable dès maintenant sur un Raspberry Pi 4, dont la personnalité (humour, sarcasme, etc...) ainsi que la voix sont customisables par l'utilisateur. Il a notamment pour but d'être plus éthique que les assistants vocaux proposés par les GAFAM, accusés à mainte reprise de surveillance audio par leurs utilisateurs.   
* [Exemples de fonctionnalités](#fonctionnalités)
* [Axes d'amélioration](#amélioration-axes)
* [Comment installer Tars](#installation)
* [Lancer Tars pour la première fois](#premier-lancement)
* [Ajouter vos propres commandes vocales](#)  
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
### Installation directe :
Une fois muni de votre Raspberry Pi et d'une carte SD vierge, rendez vous sur la section ["release"](https://), et téléchargez la version la plus récente de Tars. Ensuite, à l'aide du logiciel [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/), sélectionnez le fichier de Tars, la bonne carte SD, et cliquez sur "Write". Une fois le processus terminé, il ne vous reste plus qu'à insérer la carte SD dans votre Raspberry Pi, et vous en tenir au déroulement du [premier lancement](#premier-lancement).
### Installation du projet lui-même :
## <a id="premier-lancement">Lancer Tars pour la première fois :</a>
Avant de lancer Tars pour la première fois, il faut suivre un protocole simple en quelques étapes :
1. Branchez Tars à votre réseau via un cable ethernet. Il lui faut une connexion internet pour que vous puissiez accéder à son panneau de configuration.
2. Allumez et branchez une enceinte à Tars. C'est via cette sortie son, qu'une fois démaré, il vous donnera les instructions à suivre.
3. Branchez un microphone USB (optionnel au démarage) à votre Raspberry Pi pour que Tars puisse par la suite vous écouter
4. Alimentez Tars en électricité via un cable USB Type-C, avec une puissance suffisante pour que votre Raspberry Pi démarre.
5. Après quelques petites minutes (une ou deux), vous devriez entendre un son retentir : Tars démarre. Il ne vous reste ensuite plus qu'à suivre ses instructions.

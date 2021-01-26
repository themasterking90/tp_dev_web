Projet ISJ 5ieme année: Plateforme d’envoi de SMS

Fonctionnalités
Code 	Fonctionnalités 	Description	Pages
F1	Présentation de la plateforme	Une page d’accueil doit être développée pour 	Page d’accueil
F2	Création de compte	Tout utilisateur de la plateforme doit avoir un compte. Au moment de la création d’un compte les informations à récupérer sont : name, phoneNumber, email, country, login, password. Après la création du compte de l’utilisateur au niveau de la base de données, un email doit être envoyé au client pour vérifier son adresse email et un code doit aussi lui être envoyé par sms pour vérifier son numéro de téléphone. Le SMS sera envoyé par appel de l’api SMS http://proxysms.azieleh.com/ .
Deux attributs seront utilisés pour sauvegarder les états de vérification de l’email et du numéro de téléphone. L’attribut emailIsVerified sera utiliser pour sauvegarder l’état de vérification de l’email et phoneNumberIsVerified pour l’état de vérification du numéro de téléphone. 	Page de création de compte

Page de vérification d’email

Page de vérification de numéro de téléphone
F3 	Authentification	Tout utilisateur de la plateforme doit pouvoir s’authentifier à l’aide de son login et son password. Si l’email de l’utilisateur connecté n’a pas encore été vérifié alors, l’utilisateur doit être redirigé vers la page de vérification d’email ou bien si c’est le numéro de téléphone qui n’a pas encore été vérifié, il doit être redirigé vers la page de vérification du numéro de téléphone.	Page d’authentification
F4	Gestion des contacts de l’utilisateurs	L’utilisateur doit avoir la possibilité de gérer ses contacts : Importer au format csv, exporter au format csv, créer un contact à partir de l’interface ou consulter ses contacts. 	Page de consultation, d’export et d’import de contacts

Page de création de nouveau contact.
F5	Gestion du profil utilisateur	L’utilisateur doit avoir la possibilité de mettre à jour son profil, les informations à mettre à jour sont : apiKey, apiLogin, proxySmsUrl et toutes les informations récupérées lors de la création du compte. Il doit aussi avoir la possibilité de modifier son mot de passe.	Page de gestion de profil
F6	Gestion de message	L’utilisateur doit avoir la possibilité de gérer ses sms. Consulter les sms, exporter au format csv et créer un nouveau sms. Un sms contient les informations suivantes : le message, le ou les contacts destinataires. Une fois le sms saisi il sera envoyé au destinataire à travers l’API SMS http://proxysms.azieleh.com/ et une copie doit être sauvegardée sur la plateforme, avec le résultat de la requête reçu de l’API. 	Page de gestion des sms
Page d’envoi d’un nouveau SMS
F7	Information de gestion	L’utilisateur doit pouvoir visualiser à l’aide de tableau de bord les statistiques sur l’envoi des SMS. (Utiliser le module chartjs pour créer des graphiques statistique appropriés) 	


Règles de gestion
Code	Description
R1	L’utilisateur accède a son compte si et seulement si son email et son numéro de téléphone ont été vérifiés 
R2	L’utilisateur peut envoyer les SMS si et seulement si la valeur de l’attribut smsCredit est supérieur a 0

Documentation de l’envoi des mail à partir de l’api http://proxysms.azieleh.com/ 
Method	url	Data	Header
POST	Server	http://proxysms.azieleh.com  
Attribute	Value	Attribute	Value
			phoneNumber	Numéro 	Authorization	Basic Token
	EndPoint	/api/v0/shortMessages	message	SMS a envoyé 	Content-Type	application/json

Le Token est obtenu à partir du hash en base64 bits du la chaine de caractères suivante : apiLogin:apiKey ou apiKey et apiLogin sont des paramètres configurer dans le profil de l’utilisateur. 
Relais SMTP
Le relais SMTP permet d’envoyer les emails aux clients. Gmail offre des paramètres SMTP gratuitement, veuillez rechercher comment et les utiliser dans le cadre de ce projet
Technologies et langage de programmations
TypeScript, Framework Express, Framework Angular, Les promesses, MongoDB.


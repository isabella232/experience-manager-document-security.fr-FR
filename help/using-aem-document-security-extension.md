---
title: Utilisation d'AEM Document Security Extension for Microsoft Office
description: Vous pouvez contrôler la manière dont les destinataires utilisent vos documents protégés par une stratégie, quel que soit leur mode de distribution. Ce document explique comment protéger les fichiers et comment utiliser des fichiers protégés.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
translation-type: tm+mt
source-git-commit: 21288f7f1c8f786d3c4c363986226038bdb03e26
workflow-type: tm+mt
source-wordcount: '6270'
ht-degree: 30%

---


# Utilisation d&#39;AEM Document Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## Protection des fichiers avec AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Vous pouvez contrôler la manière dont les destinataires utilisent vos documents protégés par une stratégie, quel que soit leur mode de distribution.

Document Security Extension for Microsoft Office vous permet d&#39;effectuer les tâches suivantes :

* Configuration de votre connexion à Document Security
* Application d’une stratégie à un fichier
* Ouvrez les pages Web de Document Security pour créer et gérer les stratégies utilisateur.
* Supprimer la protection de stratégie d&#39;un fichier
* Modification de la stratégie appliquée à un fichier
* Ouvrez les pages Web de Document Security pour révoquer l’accès aux fichiers ou modifier la stratégie du fichier.
* Ouvrez les pages Web Document Security pour vue de l’historique d’audit du fichier.

### Connexion à un serveur Document Security {#connect-to-a-document-security-server}

Si vous souhaitez appliquer des stratégies à des fichiers, vous devez configurer les paramètres de connexion pour Document Security. Selon le mode d&#39;installation de Document Security Extension for Microsoft Office, vous disposez peut-être déjà de paramètres de connexion par défaut. Vous pouvez ajouter des paramètres de connexion pour une ou plusieurs instances de Document Security. Vous pouvez obtenir des informations sur le serveur auprès de l&#39;administrateur Document Security.

Vous devez définir le serveur à utiliser pour protéger les fichiers ou gérer vos fichiers protégés comme serveur par défaut. Lorsque vous appliquez une stratégie à un nouveau fichier ou que vous ouvrez les pages Web de Document Security, Document Security Extension for Microsoft Office se connecte au serveur par défaut. Si vous protégez des fichiers à l’aide de plusieurs instances de Document Security, vous devez modifier le paramètre de serveur par défaut lorsque vous passez d’un serveur à l’autre. Vous pouvez ouvrir des fichiers protégés par toute instance de Document Security tant que vous disposez de l’autorisation d’ouvrir le fichier.

Si votre serveur Document Security utilise une authentification par certificat, vous devrez installer le certificat que vous avez reçu sur votre ordinateur local. Vous devrez choisir l’authentification de certificat et fournir le certificat que vous souhaitez utiliser pour l’authentification.

Une fois que vous avez configuré les paramètres de connexion d&#39;une instance de Document Security dans une application Microsoft Office, elle est configurée pour toutes les applications Word, Excel et PowerPoint.

#### Installer le certificat côté client {#install-the-client-side-certificate}

Si vous devez accéder aux pages Web de Document Security par authentification de certificat ou authentification bidirectionnelle, vous recevrez le certificat que vous devez installer sur votre ordinateur local. Vous recevez un fichier de certificat (fichier .PFX ou .P12) et son mot de passe.

1. Enregistrez le fichier de certificat sur l’ordinateur local.
1. Doublon-cliquez sur le fichier de certificat pour ouvrir l&#39;Assistant d&#39;import de certificat et cliquez sur **Suivant**.
1. Cliquez sur **Suivant** si le fichier de certificat est répertorié dans la zone Nom de fichier. Cliquez sur **Parcourir** si vous souhaitez localiser un autre certificat.
1. Saisissez le mot de passe que vous avez reçu et cliquez sur **Suivant**.
1. Dans la boîte de dialogue Magasin de certificats, sélectionnez Placer tous les certificats dans le magasin suivant, puis cliquez sur **Parcourir**.
1. Dans la boîte de dialogue Sélectionner le magasin de certificats, sélectionnez Personnel, cliquez sur **OK**, sur **Suivant**, puis sur **Terminer**.

#### Configurer les paramètres de connexion {#configure-connection-settings}

1. Dans Document Security Extension for Microsoft, Office 2010 et Office 2013, dans l’onglet **Document Security**, sélectionnez **Sélectionner un serveur**.
1. Cliquez sur **New** pour créer de nouveaux paramètres de connexion ou sélectionnez une connexion existante et cliquez sur **Modifier**.
1. Tapez le nom de la connexion dans la zone **Name**. Vous pouvez utiliser n’importe quel nom.
1. Tapez l&#39;adresse du serveur dans la zone **Server Address**.
1. Tapez le port du serveur dans la zone **Port**.
1. (Facultatif) Si vous souhaitez mémoriser votre nom d’utilisateur et votre mot de passe, sélectionnez **Mémoriser le mot de passe sur cet ordinateur** et saisissez votre nom d’utilisateur et votre mot de passe dans les zones appropriées. Il est recommandé de ne pas sélectionner cette option si d&#39;autres personnes peuvent avoir accès à l&#39;ordinateur.
1. Cliquez sur **Se connecter à ce serveur**. Document Security Extension for Microsoft Office tente de se connecter au serveur que vous avez spécifié. Selon le type d’authentification spécifié, effectuez l’une des opérations suivantes :

   **Nom d’utilisateur et mot de passe**

   Saisissez le nom d’utilisateur et le mot de passe reçus de l’administrateur Document Security.

   **Authentification par certificat**

   Sélectionnez cette option pour sélectionner le certificat que vous avez reçu et installé dans votre magasin de certificats personnels.

   Si un seul type d&#39;authentification est configuré sur Document Security, seule cette option s&#39;affiche.

>[!NOTE]
>
>Si vous ne pouvez pas vous connecter au serveur, essayez d’ouvrir les pages Web de Document Security dans Internet Explorer. Si vous ne pouvez pas vous connecter au serveur à l’aide d’Internet Explorer ou si une boîte de dialogue affiche un avertissement concernant le certificat du serveur, Document Security Extension for Microsoft Office ne peut pas se connecter au serveur. Contactez l’administrateur du serveur pour obtenir de l’aide.

>[!NOTE]
>
>Si vous ne pouvez pas vous connecter à Document Security, un message s&#39;affiche indiquant que &quot;le nom d&#39;utilisateur et le mot de passe sont incorrects, vérifiez vos paramètres de configuration et réessayez&quot;. Ce message peut s’afficher si vous ne pouvez pas vous connecter pour une autre raison. Si vous vous connectez au serveur pour la première fois, vérifiez que vous définissez correctement le nom et le port du serveur.

#### Spécifiez le serveur par défaut {#specify-the-default-server}

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft, Office 2010 et Office 2013, dans l’onglet **Document Security**, sélectionnez **Sélectionner un serveur**.

1. Sélectionnez un serveur à spécifier comme serveur par défaut, puis cliquez sur **Définir la valeur par défaut**. Une étoile apparaît en regard du serveur par défaut.

### Utilisation de fournisseurs d’authentification tiers  {#using-third-party-authentication-providers}

Vous pouvez utiliser des fournisseurs d’authentification tiers avec AEM Forms Document Security. Ces fournisseurs d’authentification vous permettent d’ajouter une couche supplémentaire d’accès aux documents protégés. AEM Forms Document Security prend en charge les processus d’authentification étendue suivants :

* Authentification étendue à l’aide de l’URL d’AEM Forms par défaut
* Authentification étendue à l’aide d’une URL personnalisée
* Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Processus d’authentification étendue personnalisée avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Authentification étendue à l’aide d’une page personnalisée pour les listes d’authentification SAML

#### Authentification étendue à l’aide de l’URL d’AEM Forms par défaut  {#extended-authentication-using-default-aem-forms-url}

Vous pouvez utiliser l’URL par défaut d’AEM Forms pour l’authentification étendue. La page d’accueil par défaut contient l’identité graphique d’Adobe. De plus, les paramètres par défaut AEM Forms sont appliqués lors de l’utilisation de l’URL par défaut AEM Forms pour l’authentification étendue.

Effectuez les étapes suivantes pour activer l’authentification étendue avec l’URL d’accueil Adobe par défaut :

1. Ouvrez l’interface d’administration d’AEM Forms.
1. Accédez à Services > Document Security > Configuration > Configuration du serveur.
1. Activez l’option Activer l’authentification étendue.
1. Spécifiez l’URL d’accueil par défaut de l’authentification étendue. L’URL par défaut est http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Cliquez sur **[!UICONTROL Enregistrer]**.

   >[!NOTE]
   >
   >Utilisez un nom d’hôte qualifié complet dans l’URL. Il est recommandé d’utiliser le protocole HTTPS.

   Désormais, la sécurité des documents AEM Forms est configurée pour utiliser l’authentification étendue avec l’URL par défaut d’AEM Forms.

   ![](assets/third-party-authentication.png)

#### Authentification étendue avec une URL d’accueil personnalisée {#extended-authentication-with-a-custom-landing-url}

Vous pouvez utiliser une URL personnalisée pour une authentification étendue. Cela permet d’afficher une page d’authentification personnalisée avec une identité graphique personnalisée. Par exemple, l’identité graphique de votre entreprise.

Vous pouvez inclure la page d’authentification personnalisée dans un fichier war et déployer le fichier war sur le serveur AEM Forms. Le fichier war contient une logique complète pour accepter les identifiants utilisateur et s’authentifier sur le serveur AEM Forms. La sécurité des documents AEM Forms nécessite la configuration requise suivante pour la page d’authentification personnalisée :

* La page d’authentification doit envoyer le nom d’utilisateur tel que j_username et le mot de passe tel que j_password. La page doit également envoyer les paramètres source_url et login_url comme paramètres cachés.
* Une fois l’authentification réussie, la page se ferme automatiquement.

Effectuez les étapes suivantes pour activer l’authentification étendue avec une URL d’accueil personnalisée :

1. Déployez le fichier war d’authentification personnalisé sur le serveur AEM Forms.
1. Ouvrez l’interface d’administration d’AEM Forms.
1. Accédez à Services > Document Security > Configuration > Configuration du serveur.
1. Activez l’option Autoriser l’authentification étendue et spécifiez l’URL d’accueil de l’authentification étendue personnalisée.
1. Ajoutez les entrées suivantes au fichier config.xml sous le nœud SSO après l’entrée *&lt;node name=“AllowedUrls“>* :

   >[!NOTE]
   >
   >&lt;entry>!discoiqbr ! !&lt;entry>!discoiqbr ! !&lt;entry>!discoiqbr ! !

   Pour obtenir des informations détaillées sur la mise à jour du fichier config.xml, voir [Modification manuelle du fichier de configuration de la sécurité du document](https://helpx.adobe.com/fr/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Désormais, la sécurité des documents AEM Forms est configurée pour utiliser l’authentification étendue avec une URL d’accueil personnalisée

#### Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms  {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

L’authentification étendue peut utiliser différents types d’authentification disponibles sur le serveur AEM Forms. Par exemple, SAML, [Quels sont les autres exemples] ?

Remarque : si les fournisseurs SAML sont configurés sur le serveur AEM Forms, une page contenant tous les fournisseurs d’identité configurés pour les authentifications SAML s’affiche avant d’afficher l’URL d’accueil.

L’écran suivant s’affiche lorsqu’un document protégé est ouvert dans Acrobat.

#### Processus d’authentification étendue personnalisée lorsque les fournisseurs SAML sont configurés sur le serveur AEM Forms  {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Si les fournisseurs SAML sont configurés sur le serveur AEM Forms, une page contenant tous les fournisseurs d’identité configurés pour les authentifications SAML s’affiche avant d’afficher l’URL d’accueil.

La configuration requise pour l’authentification étendue personnalisée lorsque les fournisseurs SAML sont configurés sur le serveur AEM Forms est :

* Les authentifications SAML sont configurées sur le serveur d’AEM Forms
* Le fichier war personnalisé, contenant une page d’authentification personnalisée et une logique complète pour accepter les identifiants utilisateur et s’authentifier sur le serveur AEM Forms, est déployé sur le serveur AEM Forms.

#### Utilisation d’une page personnalisée pour répertorier les authentifications SAML  {#using-custom-page-for-listing-saml-authentications}

Vous pouvez également afficher une page personnalisée pour inclure tous les fournisseurs d’authentification configurés sur le serveur AEM Forms. Effectuez les étapes suivantes pour créer cette page :

1. Inclure la page d’authentification personnalisée dans un fichier war et déployer le fichier war sur le serveur AEM Forms. Le fichier war contient une logique complète pour accepter les identifiants utilisateur et s’authentifier sur le serveur AEM Forms.
1. Ouvrez l’interface d’administration d’AEM Forms et accédez à **[!UICONTROL Paramètres]**> **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Configuration]** > **[!UICONTROL Paramètres du fournisseur de services SAML]**.
1. Ajoutez l’élément suivant au champ Propriétés personnalisées et cliquez sur **[!UICONTROL Enregistrer]**.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   Désormais, la sécurité des documents AEM Forms est configurée pour afficher une page personnalisée contenant tous les fournisseurs d’authentification configurés.

### Obtention d’un compte utilisateur {#obtaining-a-user-account}

Si vous n&#39;avez pas encore de compte Document Security, Document Security peut lancer le processus d&#39;enregistrement lorsque ces événements se produisent :

* Un utilisateur Document Security qui souhaite vous envoyer un fichier protégé par une stratégie vous ajoute à une stratégie.
* L&#39;administrateur Document Security crée un compte pour vous.

Après avoir enregistré et activé votre compte, vous pouvez utiliser des fichiers protégés par une stratégie que vous avez été autorisé à utiliser par le biais d’une stratégie.

>[!NOTE]
Si vous recevez un fichier protégé par une stratégie alors que vous ne possédez pas de compte Document Security, ou si vous recevez une invitation à vous enregistrer, contactez l’expéditeur du fichier afin qu’il vous aide.

Si vous recevez une invitation à vous enregistrer par courrier électronique de Document Security, vous pouvez vous enregistrer à l’aide de l’URL du courrier électronique pour ouvrir la page d’enregistrement en ligne. Après l’enregistrement, vous recevez un second avis sur l’activation de votre compte.

#### Obtention d’un compte utilisateur externe {#obtain-an-external-user-account}

1. Ouvrez le courrier électronique d’enregistrement de Document Security. L’URL que contient le message est un lien vers la page d’enregistrement des utilisateurs externes de Document Security. Si vous ne recevez pas de message d&#39;enregistrement, contactez la personne qui vous a envoyé le dossier pour obtenir de l&#39;aide.
1. Cliquez sur l’URL ou copiez-la, puis collez-la dans le navigateur.
1. Entrez votre nom, votre organisation et votre mot de passe dans les zones appropriées. Votre mot de passe peut être n’importe quelle combinaison de huit caractères.

   >[!NOTE]
   Veillez à choisir un mot de passe facile à mémoriser ; aucune méthode n&#39;est disponible pour rechercher des mots de passe oubliés.

1. Cliquez sur **Enregistrer**. Un message s’affiche vous informant de rechercher un message électronique d’activation dans votre courrier électronique.
1. Ouvrez le courrier électronique de confirmation d&#39;inscription de Document Security.
1. Cliquez sur l’URL indiquée dans le message.
1. Cliquez sur le lien vers la page Connexion.
1. Dans la zone **Nom d’utilisateur**, saisissez l’adresse électronique à laquelle vous vous êtes inscrit auprès de Document Security. Cette adresse électronique est votre nom d’utilisateur Document Security par défaut.
1. Dans la zone **Mot de passe**, saisissez le mot de passe que vous avez créé lors de votre enregistrement.
1. Cliquez sur **Connexion**.

### Création et gestion des stratégies  {#creating-and-managing-policies}

Si vous disposez de l’autorisation de l’administrateur Document Security, vous pouvez créer des stratégies à appliquer à vos propres fichiers sur la page Stratégies des pages Web de Document Security.

Certains des paramètres de stratégie disponibles pour la création de stratégies dans les pages Web de Document Security ne sont pas pris en charge pour les fichiers Word, Excel et PowerPoint. Les tableaux suivants décrivent comment les autorisations de stratégie correspondent aux fonctionnalités Word, Excel et PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Autorisations</p></th>
   <th><p>Prise en charge de Word, Excel et PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Imprimer &gt; Non autorisé</p></td>
   <td><p>L'impression du fichier n'est pas autorisée.</p></td>
  </tr>
  <tr>
   <td><p>Imprimer &gt; Autorisé</p></td>
   <td><p>L'impression du fichier est autorisée.</p><p><strong>Remarque</strong> :  <i>Si une stratégie autorise la copie mais pas l’impression, le contenu copié dans un autre fichier peut être imprimé.</i></p></td>
  </tr>
  <tr>
   <td><p>Imprimer &gt; Faibles résolutions. Uniquement</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Tout</p></td>
   <td><p>Le fichier peut être modifié.</p><p>Lorsque cette autorisation n'est pas accordée, vous ne pouvez pas modifier les fichiers Word et Excel protégés. Vous pouvez modifier des fichiers PowerPoint, mais vous ne pouvez pas enregistrer les modifications ou les diaporamas de vue pour les fichiers modifiés.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Non autorisé</p></td>
   <td><p>Les utilisateurs ne peuvent pas modifier les fichiers protégés.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Modifier les pages</p></td>
   <td><p>Non applicable.</p><p>Inclut l’insertion, la suppression et la rotation de pages.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Fill &amp; Sign</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Hors ligne</p></td>
   <td><p>Le fichier peut être ouvert hors connexion.</p></td>
  </tr>
  <tr>
   <td><p>Copier</p></td>
   <td><p>Le contenu du fichier peut être copié dans d'autres fichiers.</p></td>
  </tr>
  <tr>
   <td><p>Reader d’écran </p></td>
   <td><p>Les lecteurs d’écran (appareils pour les utilisateurs ayant une déficience visuelle) peuvent lire le contenu du fichier.</p></td>
  </tr>
  <tr>
   <td><p>Validité des autorisations</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Paramètres généraux</p></th>
   <th><p>Prise en charge de Word, Excel et PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Période de validité</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Document d’audit</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Période de location hors connexion automatique</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Fournisseurs d’autorisations externes</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Paramètres avancés</p></th>
   <th><p>Prise en charge de Word, Excel et PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Filigranes dynamiques</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Modules externes de certification</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Algorithme de chiffrement et longueur de clé </p></td>
   <td><p>Toutes les options sont prises en charge.</p></td>
  </tr>
  <tr>
   <td><p>restriction de document</p></td>
   <td><p>Tous les contenus de fichiers sont toujours chiffrés, quel que soit le paramètre défini dans la stratégie.</p></td>
  </tr>
  <tr>
   <td><p>Message d'erreur de refus d'accès</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
 </tbody>
</table>

Pour plus d’informations sur la création et la gestion des stratégies, voir [Aide pour l’utilisateur final de Document Security](http://help.adobe.com/fr_FR/AEMForms/6.1/RMHelp/).

### Application des stratégies  {#applying-policies}

Vous pouvez appliquer toute stratégie disponible à un fichier, y compris les stratégies que vous avez créées et celles qui font partie de jeux de stratégies auxquels vous avez accès. Avant d’appliquer une stratégie, vous devez enregistrer le fichier.

Une fois la stratégie appliquée, elle est ajoutée à la liste Récemment utilisées du menu AEM Document Security afin de vous faciliter l’application des stratégies les plus fréquemment utilisées. Si vous utilisez plusieurs instances de Document Security, la liste Récemment utilisées répertorie uniquement les stratégies du serveur auquel vous êtes connecté ou du serveur par défaut si vous ne vous êtes encore connecté à aucune instance de Document Security.

>[!NOTE]
Vous pouvez appliquer des stratégies uniquement aux fichiers de documents Word (.doc, également .docx et .docm dans Microsoft Office 2010 et 2013), de classeurs Excel (.xls, également .xlsx et .xlsm dans Microsoft Office 2010 et 2013) et de présentations PowerPoint (.ppt, également .pptx et .pptm dans Microsoft 2010 et 2013). Vous ne pouvez pas appliquer de stratégies aux fichiers de modèle Word (.dot), aux fichiers de modèle Excel (.xlt) et aux fichiers de modèle de conception PowerPoint (.pot).

#### Appliquer une stratégie {#apply-a-policy}

1. Dans Document Security Extension for Microsoft Office , 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Sécuriser > Sélectionner une stratégie**.

   Si vous avez choisi le nom d’utilisateur et le mot de passe comme méthode d’authentification sur le serveur et que vous n’avez pas encore fourni d’informations de connexion à Document Security, une boîte de dialogue vous invite à saisir votre nom d’utilisateur et votre mot de passe.

1. Dans la liste, sélectionnez une stratégie, puis cliquez sur **Appliquer**.
1. Enregistrez le fichier .

#### Appliquer une stratégie récemment utilisée {#apply-a-recently-used-policy}

1. Dans Document Security Extension for Microsoft Office 2010 et 2013, sur l&#39;onglet **Document Security**, sélectionnez **Secure > ***[Nom de la stratégie]*.
1. Enregistrez le fichier.

## Utilisation des fichiers protégés par une stratégie  {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Les fichiers protégés par une stratégie contiennent la propriété intellectuelle qui appartient à l’éditeur de fichiers et est protégée par Document Security.

Vous pouvez utiliser des fichiers protégés par une stratégie, que vous soyez interne ou externe à l’entreprise de l’éditeur de fichiers. Pour ouvrir des fichiers protégés par une stratégie, vous devez être reconnu par Document Security, soit via l’insertion dans une liste LDAP ou Active Directory liée, en étant ajouté comme utilisateur local de LiveCycle ou d&#39;AEM forms on JEE, soit en vous enregistrant auprès de Document Security après avoir été invité en tant qu’utilisateur.

Si vous recevez un fichier protégé par une stratégie alors que vous ne possédez pas de compte Document Security, ou si vous recevez une invitation à vous enregistrer, contactez l’expéditeur du fichier afin qu’il vous aide.

### Utilisation des fichiers protégés par une stratégie dans Microsoft Office  {#working-with-policy-protected-files-in-microsoft-office}

Document Security Extension for Microsoft Office limite certaines fonctionnalités de Word, Excel et PowerPoint afin de protéger la propriété intellectuelle de l’éditeur de fichiers. Si vous n’êtes pas autorisé à modifier le fichier, vous ne pouvez pas y enregistrer les modifications.

Si vous travaillez avec un fichier protégé par une stratégie, il se peut que certaines fonctionnalités du produit ne soient pas disponibles ou ne fonctionnent pas comme d’habitude. Si un fichier non protégé est également ouvert, la plupart des fonctions du fichier non protégé sont activées, à l’exception de celles qui vous permettent d’importer ou de copier du contenu d’un fichier protégé par une stratégie pour lequel vous ne disposez pas des autorisations de copie ou d’exportation.

>[!NOTE]
Lorsque vous utilisez des applications Office prises en charge par Document Security Extension, il est recommandé de désactiver le paramètre Windows DEP. De plus, pour garantir le début harmonieux des applications Office sur un ordinateur équipé de Document Security Extension et de McAfee VirusScan avec activation de l&#39;option Analyse lors de l&#39;accès, désactivez l&#39;option Protection contre le débordement de la mémoire tampon dans la console McAfee VirusScan.

Si une fonction n’est pas disponible, le nom de la commande dans le menu et le bouton de barre d’outils correspondant ne sont pas disponibles. Dans Document Security Extension for Microsoft Office, lorsque vous placez le pointeur de la souris sur la commande ou le bouton, une info-bulle indique que la commande est rendue indisponible par Document Security.

### Ouverture des fichiers protégés par une stratégie  {#opening-policy-protected-files}

Vous pouvez ouvrir des fichiers protégés par une stratégie en utilisant les mêmes méthodes que celles utilisées pour ouvrir tout autre fichier. Si vous n&#39;êtes pas encore connecté à Document Security, vous êtes invité à le faire, sauf si vous n&#39;êtes pas connecté à Internet et que vous pouvez ouvrir le fichier hors connexion. Si vous annulez le processus de connexion, l’accès est refusé.

Si vous n’êtes pas autorisé à ouvrir le fichier, vous êtes informé que l’accès est refusé. Si les privilèges d’accès aux fichiers ont été révoqués, vous pouvez également être redirigé vers une version mise à jour du fichier si celle-ci est disponible. Pour obtenir une assistance supplémentaire si vous ne pouvez pas ouvrir un fichier protégé par une stratégie, contactez l’éditeur de fichiers.

Lorsqu’un fichier protégé est ouvert, le texte de la barre de titre qui suit le nom du fichier indique que le fichier est protégé par AEM Document Security.

Lors de l’ouverture d’un document protégé dans Document Security Extension for Microsoft Office à partir de SharePoint Server, assurez-vous que le programme Microsoft Office associé au type de fichier, tel que Microsoft Word, Microsoft Excel ou Microsoft PowerPoint, est ouvert. Si vous essayez d’ouvrir le fichier sans ouvrir l’application associée, le document risque de ne pas s’ouvrir et un message d’erreur indiquant que vous devez installer le module externe approprié s’affiche. Outre l’ouverture de l’application requise, il est recommandé de vider le dossier de cache avant d’ouvrir un document protégé dans Document Security Extension for Microsoft Office à partir de SharePoint Server. En outre, lorsque vous ouvrez un document protégé à partir de SharePoint Server, toutes les autorisations du document sont désactivées, quelle que soit la stratégie appliquée.

Selon la méthode d&#39;authentification mise en oeuvre sur Document Security, vous pouvez être invité à choisir la méthode d&#39;authentification lorsque vous ouvrez un document protégé. Si Document Security prend en charge plusieurs méthodes d&#39;authentification, les options d&#39;authentification vous sont présentées. Par exemple, si le serveur Document Security fournit à la fois le nom d’utilisateur/mot de passe et l’authentification par certificat, vous pouvez choisir la méthode d’authentification appropriée. Si l’authentification par certificat est activée, vous êtes invité à utiliser le certificat que vous avez reçu et installé.

L’expérience de l’utilisateur lors de l’ouverture de fichiers protégés dépend de la configuration de l’authentification mutuelle sur le serveur. Si un seul certificat client valide est installé, aucune boîte de dialogue d’authentification n’apparaît et les fichiers s’ouvrent correctement. Cependant, si plusieurs certificats clients sont installés sur un ordinateur, une boîte de dialogue d’authentification s’affiche. L’utilisateur doit choisir un certificat valide pour ouvrir le fichier protégé.

### Suppression de la protection de stratégie d’un fichier  {#removing-policy-protection-from-a-file}

Si vous êtes autorisé, vous pouvez supprimer la protection de stratégie des fichiers que vous avez protégés. Dans ce cas, le fichier n’est plus protégé par Document Security.

1. Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Supprimer**.

   Si vous n’avez pas encore fourni d’informations de connexion à Document Security, une boîte de dialogue vous invite à saisir votre nom d’utilisateur et votre mot de passe.

>[!NOTE]
Si vous ne pouvez pas supprimer une stratégie d’un fichier que vous avez protégé, contactez un administrateur Document Security.

### Affichage des paramètres de protection  {#viewing-security-settings}

Vous pouvez consulter les autorisations délivrées pour le fichier ouvert concernant l’impression, la copie, les modifications et l’accès hors connexion, ainsi que la période de validité du fichier.

Dans Document Security Extension for Microsoft Office 2010, la section Etat de la protection de l’onglet Document Security affiche vos autorisations pour le fichier.

Procédez comme suit :

* Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez un élément dans la section **Etat de la protection**.

### Enregistrement des documents lorsque l&#39;application automatique de la stratégie est activée {#saving-documents-when-auto-apply-policy-is-enabled}

Si votre administrateur a activé la fonctionnalité d’application automatique de la stratégie, tout document que vous créez ou modifiez sera automatiquement protégé lorsque vous enregistrez le document.

Si l’application automatique de la stratégie est activée, Document Security Extension for Microsoft Office vous invite à vous connecter au serveur Document Security. Vous devrez fournir votre nom d&#39;utilisateur et votre mot de passe pour être authentifié par le serveur. Si vous avez fourni les informations de connexion appropriées, le document est enregistré et protégé.

>[!NOTE]
Si vous ne pouvez pas vous connecter à Document Security, le document peut être enregistré ou non. Cela dépend de la manière dont votre administrateur a configuré la stratégie d’application automatique. Vérifiez avec l&#39;administrateur comment les documents sont traités dans cette situation.

### Synchronisation en vue de l’accès hors connexion  {#synchronizing-for-offline-access}

Les stratégies peuvent vous permettre d’ouvrir des fichiers lorsque vous êtes hors ligne et que vous n’êtes pas connecté à Document Security. Vous devez être connecté à Document Security précédemment pour établir vos informations d’identification avec le serveur avant de pouvoir travailler hors connexion. Si vous envisagez de travailler avec des fichiers hors ligne, il est recommandé de synchroniser avec Document Security avant de vous déconnecter afin de vous assurer que les paramètres de stratégie de vos fichiers sont à jour avec le serveur. Il est recommandé d’ouvrir également le fichier en ligne une fois avant de l’ouvrir hors connexion. Si vous n’ouvrez pas le fichier une seule fois en ligne ou si vous ne le synchronisez pas avec le serveur, il se peut que vous puissiez toujours utiliser des fichiers protégés par une stratégie hors ligne. Toutefois, la période d’ouverture hors connexion ne doit pas avoir expiré et les paramètres de stratégie du fichier ne doivent pas avoir été modifiés depuis la dernière synchronisation manuelle ou automatique avec le serveur.

Procédez comme suit :

* Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez l’option **Synchronisation hors connexion**.

   ***note** : Le bouton Synchroniser hors connexion est disponible même si l’utilisateur ne dispose pas d’une autorisation hors connexion pour le document. Toutefois, ce bouton est inopérant. *

### Utilisation de filigranes dynamiques {#working-with-dynamic-watermarks}

Document Security Extension for Microsoft Office prend en charge l’inclusion de filigranes dynamiques basés sur du texte dans les documents protégés par une stratégie. Un filigrane dynamique peut inclure des informations qui peuvent changer, telles que la date, l’heure, le nom d’utilisateur ou le nom de la stratégie. Si un utilisateur imprime un fichier protégé par une stratégie et que ce fichier contient un filigrane dynamique et l’autorisation d’impression, le filigrane s’affiche dans la sortie.

Document Security Extension ne prend pas en charge les fonctions de filigrane enrichies telles que les filigranes PDF, les éléments multiples d’un filigrane, les options de formatage de texte et la plage de pages.

Vous pouvez créer un filigrane dynamique en accédant aux pages Web Document Security. Pour plus d’informations sur la création de filigranes dynamiques dans un document protégé par stratégie, consultez [Aide pour l’utilisateur final de Document Security](http://www.adobe.com/go/learn_lc_euRightsMgmt_11_fr).

Document Security Extension for Microsoft Office prend en charge les fonctionnalités de filigrane suivantes :

<table>
 <thead>
  <tr>
   <th><p>Options des filigranes de sécurité document</p></th>
   <th><p>Prise en charge de Word, Excel et PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Nom de la stratégie</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Nom du filigrane</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
  <tr>
   <td><p>Utiliser comme arrière-plan</p></td>
   <td><p>Le comportement d’affichage d’un filigrane dynamique est identique, que vous sélectionniez Utiliser comme arrière-plan ou non.</p><p>Dans Word 2010 et 2013, le filigrane dynamique apparaît uniquement en mode Page et Aperçu avant impression. </p><p>Dans Excel 2010 et 2013, il apparaît également en mode Aperçu avant impression et Mise en page.</p></td>
  </tr>
  <tr>
   <td><p>Position verticale</p></td>
   <td><p>Pris en charge</p></td>
  </tr>
  <tr>
   <td><p>Position horizontale</p></td>
   <td><p>Pris en charge</p><p>Dans Excel 2010 et 2013, le positionnement horizontal des filigranes à l’aide de points ne fonctionne pas.</p></td>
  </tr>
  <tr>
   <td><p>Échelle</p></td>
   <td><p>Pris en charge</p></td>
  </tr>
  <tr>
   <td><p>Position</p></td>
   <td><p>Pris en charge</p></td>
  </tr>
  <tr>
   <td><p>Opacité</p></td>
   <td><p>Pris en charge</p></td>
  </tr>
 </tbody>
</table>

### Ouverture des pages Web de Document Security {#opening-the-document-security-web-pages}

Vous pouvez ouvrir les pages Web de Document Security pour créer et mettre à jour vos stratégies d’utilisateur, ainsi que l’état des vues et les informations d’audit sur vos fichiers protégés par une stratégie. Vous pouvez également utiliser les pages Web de Document Security pour modifier des stratégies ou révoquer l’accès à un fichier protégé par une stratégie.

Pour ouvrir les pages Web Document Security, dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Création et gestion des stratégies**. Si vous n’avez pas encore fourni vos informations de connexion, le navigateur s’ouvre à la page de connexion au serveur.

### Modification des stratégies  {#changing-policies}

Si vous disposez d’autorisations, généralement en tant qu’administrateur de Document Security ou que l’éditeur de fichiers, vous pouvez ultérieurement appliquer une autre stratégie à un fichier ou modifier les paramètres de la stratégie actuellement appliquée.

Pour modifier les paramètres d’une stratégie, utilisez les pages Web Document Security.

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft Office 2010 ou 2013, dans l’onglet **Document Security**, sélectionnez **Sécuriser > Modifier la protection**.

1. Dans la liste, sélectionnez une stratégie, puis cliquez sur **Appliquer**.

### Révocation des privilèges d’accès aux fichiers  {#revoking-file-access-privileges}

Vous pouvez révoquer la capacité d’ouvrir les fichiers que vous avez protégés. Lorsque vous révoquez les privilèges d’accès à un fichier, vous pouvez également spécifier le message qui s’affiche pour toute personne qui tente d’ouvrir le fichier et l’URL vers une version mise à jour du fichier si vous le remplacez par une copie révisée.

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Révoquer**.

   Les pages Web Document Security s’ouvrent à la page Révoquer les Documents.

1. Spécifiez un message à afficher et, si disponible, une URL pour la version mise à jour, puis cliquez sur **OK**.

Pour plus d’informations sur la révocation des privilèges d’accès aux fichiers, consultez [Aide pour l’utilisateur final de Document Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Les privilèges d’accès peuvent être rétablis via les pages Web Document Security.

### Affichage de l&#39;historique d&#39;audit des fichiers {#viewing-the-file-audit-history}

Document Security peut enregistrer l’historique des contrôles pour les fichiers protégés par une stratégie afin que vous puissiez contrôler les actions des utilisateurs sur vos fichiers.

Les événements contrôlés pour les fichiers Word, Excel et PowerPoint sont les suivants :

**Sécuriser un nouveau** documentPolicy appliqué à un fichier

**Vue** DocumentFile ouvert

**Fermer** DocumentFile fermé

**Révoquer les privilèges** DocumentAccess supprimés pour le fichier

**Annuler la révocation des privilèges** DocumentAccess renvoyés au fichier

**Modification et enregistrement local de** DocumentFile

**Imprimer le** fichier haute résolutionImprimer le fichier imprimé

**Modification de la protection** HandlerPolicy supprimée du fichier

**Changer de stratégie sur** DocumentNouvelle stratégie appliquée au fichier à partir des pages Web Document Security

### Affichage de l’historique des contrôles d’un fichier {#view-the-audit-history-for-a-file}

Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Historique des contrôles**.

Les pages Web Document Security s’ouvrent à la page Evénements, qui répertorie les événements contrôlés du fichier ouvert.

### Fonctionnalités restreintes dans Microsoft Office  {#microsoft-office-restricted-features}

Pour protéger votre propriété intellectuelle, certaines fonctionnalités de Microsoft Office ne sont pas disponibles lorsqu’un fichier protégé par une stratégie est ouvert. La liste des fonctionnalités indisponibles dépend des autorisations accordées à l’utilisateur actuel. Certaines fonctionnalités ne sont disponibles que pour un fichier protégé, tandis que d’autres ne le sont que pour tous les fichiers lorsque vous êtes dans une session protégée. En règle générale, vous êtes dans une session protégée depuis l’ouverture d’un fichier protégé par une stratégie jusqu’à la fermeture de l’application ou l’expiration de la session.

La plupart des stratégies accordent des autorisations complètes à l’éditeur de fichiers. D’autres utilisateurs peuvent remarquer d’autres restrictions sur les fonctions.

Si une commande n&#39;est pas disponible, le nom de la commande dans le menu et le bouton de barre d&#39;outils qui lui est associé sont grisés.

>[!NOTE]
L’application d’une stratégie à un fichier contenant un lien vers un fichier incorporé n’applique pas la stratégie au fichier lié. Document Security for Microsoft Office n&#39;étend pas la protection aux fichiers liés.

* Les fichiers Word, Excel et PowerPoint protégés par une stratégie ne peuvent pas s’ouvrir dans une fenêtre du navigateur Internet Explorer.
* Les utilisateurs qui n&#39;ont obtenu que l&#39;autorisation Modifier ne peuvent pas copier du contenu dans un fichier à partir d&#39;une autre application à l&#39;aide du Presse-papiers Windows. Les utilisateurs peuvent copier du contenu dans des fichiers en activant l&#39;option Presse-papiers de Microsoft Office.
* L’ouverture d’un fichier protégé par une stratégie dans Microsoft Office rend la clé d’écran d’impression indisponible jusqu’à ce que vous fermiez l’application ou que la session expire.
* Document Security for Microsoft Office ne prend pas en charge Web-based Distributed Authoring and Versioning (WebDAV). Dans la plupart des cas, vous ne pouvez pas ouvrir un fichier protégé par une stratégie à partir d’un dossier WebDAV. Si vous pouvez ouvrir un fichier protégé par une stratégie, vous n’avez pas l’autorisation d’enregistrer, d’imprimer, de modifier ou de copier le fichier.

La protection générale appliquée aux fichiers protégés par une stratégie comprend les restrictions suivantes :

De nombreuses fonctionnalités courantes peuvent être restreintes dans Word, Excel et PowerPoint au cours d’une session protégée.

Si un fichier protégé par une stratégie qui ne permet pas à l’utilisateur d’apporter des modifications est ouvert, les commandes qui modifient le fichier de quelque manière que ce soit ne sont pas disponibles. Seules les commandes qui ouvrent ou créent de nouveaux documents et modifient les préférences de l’application sont disponibles.

#### Restrictions de Word 2010 et de Word 2013 {#word-2010-and-word-2013-restrictions}

L’ouverture d’un fichier protégé par une stratégie dans Word rend inaccessible l’enregistrement des informations de récupération automatique de fichiers jusqu’à ce que vous fermiez et redémarriez Word. En outre, les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations décrites ci-dessous :

**Fichier > Nouveau > Nouveau à partir d’un fichier** existantDisponible, mais les fichiers créés à l’aide de cette commande alors qu’un fichier protégé par une stratégie est ouvert ne peuvent pas être enregistrés. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier >** EnregistrerRestreint par l’autorisation Modifier.

**Fichier > Enregistrer sous** tout, options restreintes par l’autorisation Modifier.

**Options Fichier >** ImprimerToutes restreintes par l’autorisation d’impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Options Fichier > Enregistrer et** EnvoyerTous indisponibles pendant une session protégée.

**Fichier > Infos > Document Protect > Chiffrer avec mot de passe, Ajouter la signature numérique, Marquer comme final, Restreindre l’autorisation par** des personnesNon disponible pendant une session protégée.

**Fichier >** ProcessusNon disponible pendant une session protégée.

***Remarque ** : La fonction de démarrage d’un flux de travaux à partir des versions Microsoft Office 2010 de Word, Excel et PowerPoint est disponible uniquement dans les suites Office Professional Plus 2010, Office Enterprise 2010 et Office Ultimate 2010, ainsi que dans les versions Office 2010 autonomes de ces programmes.*

**Publication de blog >** PublierNon disponible pendant une session protégée.

**Fichier > Serveur > Fichier Server Tâches** MenuNon disponible pendant une session protégée.

**Accueil > Presse-papiers >** CopierRestreint par l’autorisation Copier. Si la copie n&#39;est pas autorisée, le contenu copié ne peut pas être collé dans un autre fichier ou dans le Presse-papiers Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers >** CollerRestreint par l’autorisation Modifier.

**Accueil > Presse-papiers > Coller** spécialRestreint par l&#39;autorisation Modifier.

**Insertion > Texte >** ObjetNon disponible pendant une session protégée. Les fichiers protégés par une stratégie ne peuvent pas être insérés à tout moment.

**** MessagesLa plupart des options de cet onglet ne sont pas disponibles pendant une session protégée.

**Révision > Vérification >** RechercheRestreinte par l&#39;autorisation Copier. Non disponible si la copie n&#39;est pas autorisée.

**Révision > Vérification >** ThésaurusRestreint par l’autorisation Copier. Non disponible si la copie n&#39;est pas autorisée.

**Révision > Langue > Traduire > Traduire** DocumentEnabled avec l’autorisation Copier.

**Révision > Langue > Traduire > Traduire le** texte sélectionnéActivé avec l’autorisation Copier.

**Révision > Langue > Traduction > Mini** TranslatorEnabled avec l’autorisation Copier.

**Révision > Comparer >** ComparerNon disponible pendant une session protégée. Les fichiers protégés par une stratégie ne peuvent être comparés à aucun moment.

**Révision > Protect >** Auteurs de blocsNon disponible pendant une session protégée.

**Revoir > Protect > Restreindre l’** éditionNon disponible pendant une session protégée.

**Vue >** MacrosCertaines macros sont restreintes par l’autorisation Copier et ne sont pas disponibles, sauf si la copie est autorisée.

**Ajoute-** insImpossible d&#39;ajouter ou de supprimer une session protégée.

**** Collaboration en ligneNon disponible pendant une session protégée.

**Principal et** sous-documentsLes sous-documents sont régis par la stratégie des documents maîtres lorsqu&#39;ils sont ouverts dans le document maître. S’ils sont ouverts séparément, les sous-documents ne peuvent pas être imprimés, copiés ou modifiés.

**** ResummarizeUnavailable pendant une session protégée.

**Images (et toutes les commandes associées)** Non disponibles pendant une session protégée.

**Document** PanelUnavailable pendant une session protégée.

**Développeur > Document** TemplateUnavailable pendant une session protégée. Pour accéder à cette commande, choisissez Fichier > Options > Personnaliser > Onglet Développeur > Modèles > Modèle de Document.

**Contour > Document de Principal > Créer un sous-document, Insérer un** sous-documentNon disponible pendant une session protégée.

#### Restrictions dans Excel 2010 et Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations suivantes :

**Fichier > Nouveau > Nouveau à partir d’** ExistingAvailable, mais les fichiers créés à l’aide de cette commande au cours d’une session protégée ne peuvent pas être enregistrés. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier > Enregistrer, Enregistrer sous** restreint par l’autorisation Modifier.

**Fichier > Enregistrer sous >** PDFUndisponible pendant une session protégée.

**Fichier >** ImprimerRestreint par l’autorisation d’impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Fichier > Infos > Protect** DocumentNon disponible pendant une session protégée.

**Fichier > Infos >** Classeur ProtectNon disponible pendant une session protégée.

**Fichier > Enregistrer et** EnvoyerNon disponible pendant une session protégée.

**Fichier > Options > Ajoutes-** insImpossible d&#39;ajouter ou de supprimer une session protégée.

**Fichier >** ProcessusNon disponible pendant une session protégée.

***Remarque ** : La fonction de démarrage d’un flux de travaux à partir des versions Microsoft Office 2010 de Word, Excel et PowerPoint est disponible uniquement dans les suites Office Professional Plus 2010, Office Enterprise 2010 et Office Ultimate 2010, ainsi que dans les versions Office 2010 autonomes de ces programmes.*

**Fichier > Serveur > Fichier Server Tâches** MenuNon disponible pendant une session protégée.

**Accueil > Presse-papiers >** CopierRestreint par l’autorisation Copier. Si la copie n&#39;est pas autorisée, le contenu copié ne peut pas être collé dans un autre fichier ou dans le Presse-papiers Microsoft Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers >** CollerRestreint par l’autorisation Modifier.

**Accueil > Presse-papiers > Coller** spécialRestreint par l&#39;autorisation Modifier.

**Accueil > Cellules > Format > Déplacer ou Copier la** feuilleNon disponible pendant une session protégée.

**Accueil > Cellules > Insérer > Insérer une** feuilleNon disponible pendant une session protégée.

**Accueil > Cellules > Supprimer > Supprimer la** feuilleNon disponible pendant une session protégée.

**Accueil > Edition > Remplir > Sur** une feuille de calculRestreint par l&#39;autorisation Modifier.

**Insertion > Tableaux >** TableauRestreint par l&#39;autorisation Modifier.

**Impossible de sélectionner Insertion > Tableaux > Fichiers protégés par une stratégie de tableau** croisé dynamique dans l&#39;Assistant Création.

**Insertion > Texte >** ObjetNon disponible pendant une session protégée. Les fichiers protégés par une stratégie ne peuvent pas être insérés à tout moment.

**Insertion > Texte > En-tête et** pied de pageRestreint par l’autorisation Modifier. Non disponible pour un document protégé par une stratégie.

**Les données > Obtenir des** données externesData à partir de fichiers protégés par une stratégie ne peuvent pas être importées.

**Données > Plan >** Sous-totauxRestreint par l’autorisation Modifier.

**Données > Outils de données >** Validation de donnéesRestreint par l’autorisation Modifier.

**Révision > Vérification >** RechercheRestreinte par l&#39;autorisation Copier.

**Révision > Vérification >** ThésaurusRestreint par l’autorisation Copier.

**Révision > Langue >** TraduireRestreint par l’autorisation Copier.

**Révision > Modifications > Protect** SheetNon disponible pendant une session protégée.

**Révision > Modifications >** Classeur ProtectNon disponible pendant une session protégée.

**Révision > Modifications > Partager le** classeurNon disponible pendant une session protégée.

**Révision > Modifications > Protect et partager le** classeurNon disponible pendant une session protégée.

**Révision > Modifications > Autoriser les utilisateurs à modifier des** plagesNon disponible pendant une session protégée.

**Révision > Modifications > Suivi des modifications > Mettre en surbrillance les** modificationsNon disponible pour un fichier protégé par une stratégie qui contient un filigrane dynamique.

**Vue >** MacrosRestreinte par l’autorisation Modifier.

**Vue > Enregistrer** WorkspaceCommand ne fonctionne pas.

**Développeur > XML >** Packs d&#39;extensionCertaines macros sont restreintes par l&#39;autorisation Copier et ne sont pas disponibles, sauf si la copie est autorisée.

**Formules > Contrôle des formules > Erreur** ContrôleRestreint par l’autorisation Modifier. Non disponible sauf si la modification est autorisée.

**** Collaboration en ligneNon disponible pendant une session protégée.

**Enregistrer les** informations de récupération automatique indisponibles pendant une session protégée.

***Remarque ** : Si vous tentez de modifier une cellule dans un fichier protégé par une stratégie pour lequel vous n’êtes pas autorisé à effectuer des modifications, Excel affiche un message d’avertissement pour une opération incorrecte et vous indique que vous devez ôter la protection du fichier à l’aide de la commande Ôter la protection de la feuille. L’utilisation de cette commande ne supprime pas la protection de stratégie du fichier.*

#### Restrictions dans PowerPoint 2010 et PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations suivantes :

**Fichier > Nouveau > Nouveau à partir d’** ExistingAvailable, mais les fichiers créés à l’aide de cette commande au cours d’une session protégée ne peuvent pas être enregistrés. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier >** EnregistrerRestreint par l’autorisation Modifier.

**Fichier > Enregistrer sous** tout, options restreintes par l’autorisation Modifier.

**Options Fichier >** ImprimerToutes restreintes par l’autorisation d’impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Fichier > Enregistrer et** EnvoyerNon disponible pendant une session protégée.

**Fichier > Infos > Présentation Protect > Chiffrer par mot de passe, Ajouter une signature numérique, Marquer comme final, Restreindre l&#39;autorisation par** les personnes indisponibles pendant une session protégée.

**Fichier > Options PowerPoint > Enregistrer les** informations de récupération automatique indisponibles pendant une session protégée.

**Fichier > Serveur > Fichier Server Tâches** MenuNon disponible pendant une session protégée.

**Accueil > Presse-papiers >** CopierRestreint par l’autorisation Copier. Si la copie n&#39;est pas autorisée, le contenu copié ne peut pas être collé dans le document, dans un autre fichier ou dans le Presse-papiers Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers >** CollerRestreint par l’autorisation Modifier. Si la copie n’est pas autorisée, le contenu copié ne peut pas être collé dans le document.

**Accueil > Presse-papiers > Coller** spécialRestreint par l&#39;autorisation Modifier.

**Accueil > Diapositives > Nouvelles diapositives > Diapositives d&#39;un plan, réutiliser** les diapositivesNon disponible pendant une session protégée.

**Insertion > Texte >** ObjetNon disponible pendant une session protégée. Les fichiers protégés par une stratégie ne peuvent pas être insérés à tout moment.

**Création > Arrière-plan > Styles d’arrière-plan, Masquer les graphiques d’arrière-plan, Format** Arrière-planNon disponible pour un fichier protégé par une stratégie qui contient un filigrane dynamique.

**Diaporama > Configurer > Enregistrer le** diaporamaRestreint par l&#39;autorisation de modification.

**Révision > Vérification >** ThésaurusRestreint par l’autorisation Copier.

**Révision > Langue >** TraduireRestreint par l’autorisation Copier.

**Révision > Langue > Traduction > Mini** TranslatorEnabled avec l’autorisation Copier.

**Vue > Vues de présentation > Diaporama** restreint par l’autorisation Modifier. Si les modifications ne sont pas autorisées, les diaporamas ne peuvent pas être affichés si le fichier a été modifié.

**Vue >** MacrosCertaines macros sont restreintes par l’autorisation Copier et ne sont pas disponibles, sauf si la copie est autorisée.

**Ajoute-** insImpossible d&#39;ajouter ou de supprimer une session protégée.

**** Collaboration en ligneNon disponible pendant une session protégée.

## Utilisation de fournisseurs d’authentification tiers {#use-third-party-authentication-providers}

Vous pouvez utiliser des fournisseurs d’authentification tiers avec AEM Forms Document Security. Ces fournisseurs d’authentification vous permettent d’ajouter une couche supplémentaire d’accès aux documents protégés. AEM Forms Document Security prend en charge les processus d’authentification étendue suivants :

* Authentification étendue à l’aide de l’URL d’AEM Forms par défaut
* Authentification étendue à l’aide d’une URL personnalisée
* Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Processus d’authentification étendue personnalisée avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Authentification étendue à l’aide d’une page personnalisée pour les listes d’authentification SAML

Pour connaître la procédure détaillée de configuration des processus d&#39;authentification étendue, reportez-vous à l&#39;article [Scénarios d&#39;authentification étendue](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)

## Glossaire   {#glossary}

Pour plus d&#39;informations sur la terminologie LiveCycle et AEM forms on JEE, consultez le [Glossaire](http://www.adobe.com/go/learn_aemforms_designer_65_fr).

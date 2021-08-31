---
title: Utilisation d’AEM Document Security Extension for Microsoft Office
description: Vous pouvez contrôler la manière dont les destinataires utilisent vos documents protégés par une stratégie, quel que soit leur mode de distribution. Ce document explique comment protéger les fichiers et comment utiliser des fichiers protégés.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 13c487b13acb0d65f02301c881bfade512428bcd
workflow-type: tm+mt
source-wordcount: '6252'
ht-degree: 100%

---

# Utilisation d’AEM Document Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## Protection des fichiers avec AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Vous pouvez contrôler la manière dont les destinataires utilisent vos documents protégés par une stratégie, quel que soit leur mode de distribution.

Document Security Extension for Microsoft Office permet d’effectuer les tâches suivantes :

* Configuration de la connexion à Document Security
* Application d’une politique à un fichier
* Ouverture des pages web de Document Security pour créer et gérer les stratégies utilisateur.
* Suppression de la protection de stratégie d’un fichier
* Changement de la stratégie appliquée à un fichier
* Ouverture des pages web de Document Security pour révoquer l’accès aux fichiers ou modifier la stratégie relative au fichier.
* Ouverture des pages web de Document Security pour afficher l’historique d’audit du fichier

### Connexion à un serveur Document Security {#connect-to-a-document-security-server}

Si vous souhaitez appliquer des stratégies à des fichiers, vous devez configurer les paramètres de connexion à Document Security. Selon le mode d’installation de Document Security Extension for Microsoft Office, vous disposez peut-être déjà de paramètres de connexion par défaut. Vous pouvez ajouter des paramètres de connexion pour une ou plusieurs instances de Document Security. Il est possible d’obtenir des informations sur le serveur auprès de l’administrateur de Document Security.

Vous devez définir le serveur à utiliser pour protéger les fichiers ou gérer vos fichiers protégés à titre de serveur par défaut. Lorsque vous appliquez une stratégie à un nouveau fichier ou que vous ouvrez les pages web de Document Security, Document Security Extension for Microsoft Office se connecte au serveur par défaut. Si vous protégez des fichiers à l’aide de plusieurs instances de Document Security, vous devez modifier le paramètre de serveur par défaut lorsque vous passez d’un serveur à l’autre. Vous pouvez ouvrir des fichiers protégés par toute instance de Document Security tant que vous disposez de l’autorisation d’ouvrir un fichier.

Si le serveur Document Security utilise une authentification par certificat, vous devrez installer celui reçu sur votre ordinateur local. Vous devrez choisir l’authentification de certificat et fournir celui que vous souhaitez utiliser pour l’authentification.

Une fois les paramètres de connexion d’une instance de Document Security configurés dans une application Microsoft Office, elle est configurée pour toutes les applications Word, Excel et PowerPoint.

#### Installation du certificat côté client {#install-the-client-side-certificate}

Si vous devez accéder aux pages web de Document Security par authentification de certificat ou authentification bidirectionnelle, vous recevrez le certificat que vous devez installer sur votre ordinateur local. Vous recevez un fichier de certificat (fichier .PFX ou .P12) et son mot de passe.

1. Enregistrez le fichier de certificat sur l’ordinateur local.
1. Double-cliquez sur le fichier de certificat pour ouvrir l’assistant d’import de certificat, puis cliquez sur **Suivant**.
1. Cliquez sur **Suivant** si le fichier de certificat est répertorié dans la zone Nom de fichier. Cliquez sur **Parcourir** si vous souhaitez localiser un autre certificat.
1. Saisissez le mot de passe que vous avez reçu et cliquez sur **Suivant**.
1. Dans la boîte de dialogue Magasin de certificats, sélectionnez Placer tous les certificats dans le magasin suivant, puis cliquez sur **Parcourir**.
1. Dans la boîte de dialogue Sélectionner le magasin de certificats, sélectionnez Personnel, cliquez sur **OK**, sur **Suivant**, puis sur **Terminer**.

#### Configurer les paramètres de connexion {#configure-connection-settings}

1. Dans Document Security Extension for Microsoft, Office 2010 et Office 2013, dans l’onglet **Document Security**, sélectionnez **Sélectionner un serveur**.
1. Cliquez sur **Nouveau** pour créer de nouveaux paramètres de connexion ou sélectionnez une connexion existante et cliquez sur **Modifier**.
1. Tapez un nom de connexion dans la zone **Nom**. Vous pouvez utiliser n’importe quel nom.
1. Tapez l’adresse du serveur dans la zone **Adresse du serveur**.
1. Saisissez le port du serveur dans la zone **Port**.
1. (Facultatif) Si vous souhaitez mémoriser votre nom d’utilisateur et votre mot de passe, sélectionnez **Mémoriser le mot de passe sur cet ordinateur** et saisissez votre nom d’utilisateur et votre mot de passe dans les zones appropriées. Il est recommandé de ne pas sélectionner cette option si d’autres personnes peuvent avoir accès à l’ordinateur.
1. Cliquez sur **Se connecter à ce serveur**. Document Security Extension for Microsoft Office tente de se connecter au serveur que vous avez spécifié. Selon le type d’authentification spécifié, effectuez l’une des opérations suivantes :

   **Nom d’utilisateur et mot de passe**

   Saisissez le nom d’utilisateur et le mot de passe reçus de l’administrateur Document Security.

   **Authentification par certificat**

   Choisissez cette option pour sélectionner le certificat que vous avez reçu et installé dans votre magasin de certificats personnel.

   Si un seul type d’authentification est configuré pour Document Security, seule cette option s’affiche.

>[!NOTE]
>
>Si vous ne pouvez pas vous connecter au serveur, essayez d’ouvrir les pages web de Document Security dans Internet Explorer. Si vous ne pouvez pas vous connecter au serveur à l’aide d’Internet Explorer ou si une boîte de dialogue affiche un avertissement concernant le certificat du serveur, Document Security Extension for Microsoft Office ne peut pas se connecter au serveur. Contactez l’administrateur du serveur pour obtenir de l’aide.

>[!NOTE]
>
>Si vous ne pouvez pas vous connecter à Document Security, un message s’affiche indiquant : « Le nom d’utilisateur et/ou le mot de passe sont incorrects. Vérifiez vos paramètres de configuration, puis réessayez. ». Ce message peut s’afficher si vous ne pouvez pas vous connecter pour une autre raison. Si vous vous connectez au serveur pour la première fois, vérifiez que vous définissez correctement le nom et le port du serveur.

#### Spécifiez le serveur par défaut {#specify-the-default-server}

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft, Office 2010 et Office 2013, dans l’onglet **Document Security**, sélectionnez **Sélectionner un serveur**.

1. Sélectionnez un serveur défini par défaut, puis cliquez sur **Définir la valeur par défaut**. Une étoile apparaît en regard du serveur par défaut.

### Utilisation de fournisseurs d’authentification tiers {#using-third-party-authentication-providers}

Vous pouvez utiliser des fournisseurs d’authentification tiers avec AEM Forms Document Security. Ces fournisseurs d’authentification vous permettent d’ajouter une couche supplémentaire d’accès aux documents protégés. AEM Forms Document Security prend en charge les processus d’authentification étendue suivants :

* Authentification étendue à l’aide de l’URL d’AEM Forms par défaut
* Authentification étendue à l’aide d’une URL personnalisée
* Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Processus d’authentification étendue personnalisée avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Authentification étendue à l’aide d’une page personnalisée pour les listes d’authentification SAML

#### Authentification étendue à l’aide de l’URL d’AEM Forms par défaut {#extended-authentication-using-default-aem-forms-url}

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
   >&lt;entry key=”sso-l” value=”/ sample_/login.jsp”/>!!discoiqbr!!&lt;entry key=”sso-s” value=”/ sample_/welcome.jsp”>!!discoiqbr!!&lt;entry key=”sso-o” value=”/ sample_/logout.jsp”/>!!discoiqbr!!

   Pour obtenir des informations détaillées sur la mise à jour du fichier config.xml, voir [Modification manuelle du fichier de configuration de la sécurité du document](https://helpx.adobe.com/fr/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Désormais, la sécurité des documents AEM Forms est configurée pour utiliser l’authentification étendue avec une URL d’accueil personnalisée

#### Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

L’authentification étendue peut utiliser différents types d’authentification disponibles sur le serveur AEM Forms. Par exemple, SAML, [D’autres exemples].

Remarque : si les fournisseurs SAML sont configurés sur le serveur AEM Forms, une page contenant tous les fournisseurs d’identité configurés pour les authentifications SAML s’affiche avant d’afficher l’URL d’accueil.

L’écran suivant s’affiche lorsqu’un document protégé est ouvert dans Acrobat.

#### Processus d’authentification étendue personnalisée lorsque les fournisseurs SAML sont configurés sur le serveur AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Si les fournisseurs SAML sont configurés sur le serveur AEM Forms, une page contenant tous les fournisseurs d’identité configurés pour les authentifications SAML s’affiche avant d’afficher l’URL d’accueil.

La configuration requise pour l’authentification étendue personnalisée lorsque les fournisseurs SAML sont configurés sur le serveur AEM Forms est :

* Les authentifications SAML sont configurées sur le serveur d’AEM Forms
* Le fichier war personnalisé, contenant une page d’authentification personnalisée et une logique complète pour accepter les identifiants utilisateur et s’authentifier sur le serveur AEM Forms, est déployé sur le serveur AEM Forms.

#### Utilisation d’une page personnalisée pour répertorier les authentifications SAML {#using-custom-page-for-listing-saml-authentications}

Vous pouvez également afficher une page personnalisée pour inclure tous les fournisseurs d’authentification configurés sur le serveur AEM Forms. Effectuez les étapes suivantes pour créer cette page :

1. Inclure la page d’authentification personnalisée dans un fichier war et déployer le fichier war sur le serveur AEM Forms. Le fichier war contient une logique complète pour accepter les identifiants utilisateur et s’authentifier sur le serveur AEM Forms.
1. Ouvrez l’interface d’administration d’AEM Forms et accédez à **[!UICONTROL Paramètres]** > **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Configuration]** > **[!UICONTROL Paramètres du fournisseur de services SAML]**.
1. Ajoutez l’élément suivant au champ Propriétés personnalisées et cliquez sur **[!UICONTROL Enregistrer]**.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   Désormais, la sécurité des documents AEM Forms est configurée pour afficher une page personnalisée contenant tous les fournisseurs d’authentification configurés.

### Obtention d’un compte utilisateur {#obtaining-a-user-account}

Si vous n’avez pas encore de compte Document Security, Document Security peut lancer le processus d’enregistrement lorsque les événements suivants se produisent :

* Un utilisateur de Document Security qui souhaite vous envoyer un fichier protégé par une stratégie vous ajoute à une stratégie.
* Un administrateur de Document Security vous crée un compte.

Après vous être enregistré et avoir activé votre compte, vous pouvez utiliser les fichiers protégés par une stratégie pour lesquels vous disposez d’une autorisation.

>[!NOTE]
>
>Si vous recevez un fichier protégé par une stratégie alors que vous ne possédez pas de compte Document Security, ou si vous recevez une invitation à vous enregistrer, contactez l’expéditeur du fichier afin qu’il vous aide.

Si vous recevez une invitation à vous enregistrer par email à l’aide de Document Security, vous pouvez vous enregistrer à l’aide de l’URL indiquée pour ouvrir la page d’enregistrement en ligne. Après l’enregistrement, vous recevez un second avis sur l’activation de votre compte.

#### Obtention d’un compte utilisateur externe {#obtain-an-external-user-account}

1. Ouvrez l’email d’inscription de Document Security. L’URL contenue dans le message est un lien vers la page d’enregistrement des utilisateurs externes de Document Security. Si vous ne recevez pas de message d’enregistrement, contactez la personne qui vous a adressé le dossier pour obtenir de l’aide.
1. Cliquez sur l’URL ou copiez-la, puis collez-la dans le navigateur.
1. Entrez votre nom, votre organisation et votre mot de passe dans les zones appropriées. Votre mot de passe peut être n’importe quelle combinaison de huit caractères.

   >[!NOTE]
   >
   >Veillez à choisir un mot de passe facile à retenir ; aucune méthode n’est proposée pour rechercher des mots de passe oubliés.

1. Cliquez sur **Enregistrer**. Un message s’affiche pour vous demander de vérifier votre adresse électronique en vue d’envoyer un email d’activation.
1. Ouvrez l’email de confirmation d’enregistrement de Document Security.
1. Cliquez sur l’URL indiquée dans le message.
1. Cliquez sur le lien vers la page Ouverture de session.
1. Dans le champ **Nom d’utilisateur**, saisissez l’adresse électronique à l’aide de laquelle vous vous êtes enregistré auprès de Document Security. Cette adresse correspond à votre nom d’utilisateur Document Security par défaut.
1. Dans le champ **Mot de passe**, saisissez le mot de passe créé lors de votre enregistrement.
1. Cliquez sur **Ouverture de session**.

### Création et gestion des stratégies {#creating-and-managing-policies}

Si vous disposez de l’autorisation de l’administrateur Document Security, vous pouvez créer des stratégies applicables à vos propres fichiers dans la page Stratégies des pages web de Document Security.

Certains des paramètres disponibles pour la création de stratégies dans les pages web de Document Security ne sont pas pris en charge pour les fichiers Word, Excel et PowerPoint. Les tableaux suivants décrivent les correspondances des autorisations de stratégie avec les fonctionnalités Word, Excel et PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Autorisations</p></th>
   <th><p>Prise en charge de Word, Excel et PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Imprimer &gt; Non autorisé</p></td>
   <td><p>L’impression du fichier n’est pas autorisée.</p></td>
  </tr>
  <tr>
   <td><p>Imprimer &gt; Autorisé</p></td>
   <td><p>L’impression du fichier est autorisée.</p><p><strong>Remarque</strong> : <i>Si une stratégie autorise la copie, mais pas l’impression, il est possible d’imprimer le contenu copié dans un autre fichier.</i></p></td>
  </tr>
  <tr>
   <td><p>Imprimer &gt; Basse résolution uniquement</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Tout</p></td>
   <td><p>Le fichier peut être modifié.</p><p>Lorsque cette autorisation n’est pas accordée, vous ne pouvez pas modifier les fichiers Word et Excel protégés. Vous pouvez modifier des fichiers PowerPoint, mais vous ne pouvez pas enregistrer les modifications ou afficher les diaporamas pour les fichiers modifiés.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Non autorisé</p></td>
   <td><p>Les utilisateurs ne peuvent pas modifier les fichiers protégés.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Modifier les pages</p></td>
   <td><p>Non applicable.</p><p>Inclut insérer, supprimer et faire pivoter des pages.</p></td>
  </tr>
  <tr>
   <td><p>Modifier &gt; Remplir et signer</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Hors connexion</p></td>
   <td><p>Le fichier peut être ouvert hors connexion.</p></td>
  </tr>
  <tr>
   <td><p>Copier</p></td>
   <td><p>Le contenu du fichier peut être copié dans d’autres fichiers.</p></td>
  </tr>
  <tr>
   <td><p>Lecteur d’écran </p></td>
   <td><p>Les lecteurs d’écran (appareils pour les utilisateurs atteints de déficience visuelle) peuvent lire le contenu du fichier.</p></td>
  </tr>
  <tr>
   <td><p>Validité des droits</p></td>
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
   <td><p>Période d’ouverture hors connexion</p></td>
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
   <td><p>Plug-ins de certification</p></td>
   <td><p>Non applicable.</p></td>
  </tr>
  <tr>
   <td><p>Algorithme de chiffrement et longueur des clés </p></td>
   <td><p>Toutes les options sont prises en charge.</p></td>
  </tr>
  <tr>
   <td><p>Restrictions du document</p></td>
   <td><p>Tous les contenus des fichiers sont toujours chiffrés, quel que soit le paramètre défini dans la stratégie.</p></td>
  </tr>
  <tr>
   <td><p>Message d’erreur de refus d’accès</p></td>
   <td><p>Pris en charge.</p></td>
  </tr>
 </tbody>
</table>

Pour plus d’informations sur la création et la gestion des stratégies, voir [Aide pour l’utilisateur final de Document Security](http://help.adobe.com/fr_FR/AEMForms/6.1/RMHelp/).

### Application des stratégies {#applying-policies}

Vous pouvez appliquer les stratégies disponibles à un fichier, y compris celles que vous avez créées et celles qui font partie de jeux de stratégies auxquels vous avez accès. Avant d’appliquer une stratégie, vous devez enregistrer le fichier.

Une fois la stratégie appliquée, elle est ajoutée à la liste Récemment utilisées du menu AEM Document Security afin de vous faciliter l’application des stratégies les plus fréquemment utilisées. Si vous utilisez plusieurs instances de Document Security, la liste Récemment utilisées répertorie uniquement les stratégies du serveur auquel vous êtes connecté ou du serveur par défaut si vous ne vous êtes encore connecté à aucune instance de Document Security.

>[!NOTE]
>
>Vous pouvez appliquer des stratégies uniquement aux fichiers de documents Word (.doc, également .docx et .docm dans Microsoft Office 2010 et 2013), de classeurs Excel (.xls, également .xlsx et .xlsm dans Microsoft Office 2010 et 2013) et de présentations PowerPoint (.ppt, également .pptx et .pptm dans Microsoft 2010 et 2013). Vous ne pouvez pas appliquer de stratégies aux fichiers de modèle Word (.dot), aux fichiers de modèle Excel (.xlt) ni aux fichiers de modèle de conception PowerPoint (.pot).

#### Application d’une stratégie {#apply-a-policy}

1. Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Sécuriser > Sélectionner une stratégie**.

   Si vous avez choisi le nom d’utilisateur et le mot de passe comme méthode d’authentification sur le serveur et que vous n’avez pas encore fourni d’informations de connexion à Document Security, une boîte de dialogue vous invite à saisir votre nom d’utilisateur et votre mot de passe.

1. Dans la liste, sélectionnez une stratégie, puis cliquez sur **Appliquer**.
1. Enregistrez le fichier.

#### Application d’une stratégie récemment utilisée {#apply-a-recently-used-policy}

1. Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Sécuriser** > *[Nom de la stratégie]*.
1. Enregistrez le fichier.

## Utilisation des fichiers protégés par une stratégie {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Les fichiers protégés par une stratégie contiennent la propriété intellectuelle appartenant à l’éditeur de fichiers et protégés à l’aide de Document Security.

Vous pouvez utiliser des fichiers protégés par une stratégie en interne comme à l’extérieur de l’entreprise de l’éditeur de fichiers. Pour ouvrir des fichiers protégés par une stratégie, vous devez être reconnu par Document Security, soit via l’insertion dans une liste LDAP ou Active Directory liée, en étant ajouté comme utilisateur local de LiveCycle ou d’AEM forms on JEE, soit en vous enregistrant auprès de Document Security après avoir été invité en tant qu’utilisateur.

Si vous recevez un fichier protégé par une stratégie alors que vous ne possédez pas de compte Document Security, ou si vous recevez une invitation à vous enregistrer, contactez l’expéditeur du fichier afin qu’il vous aide.

### Utilisation des fichiers protégés par une stratégie dans Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}

Document Security Extension for Microsoft Office limite certaines fonctionnalités de Word, Excel et PowerPoint afin de protéger la propriété intellectuelle de l’éditeur de fichiers. Si vous n’êtes pas autorisé à modifier le fichier, vous ne pouvez pas y enregistrer les modifications.

Si vous travaillez avec un fichier protégé par une stratégie, il se peut que certaines fonctionnalités du produit ne soient pas disponibles ou ne fonctionnent pas comme d’habitude. Si un fichier non protégé est également ouvert, la plupart des fonctions du fichier non protégé sont activées, à l’exception de celles qui vous permettent d’importer ou de copier du contenu d’un fichier protégé par une stratégie pour lequel vous ne disposez pas des autorisations de copie ou d’exportation.

>[!NOTE]
>
>Lorsque vous utilisez des applications Office prises en charge par Document Security Extension, il est recommandé de désactiver le paramètre Windows DEP. En outre, pour garantir le démarrage correct des applications Office sur un ordinateur doté de Document Security Extension et de McAfee VirusScan avec activation de l’option d’analyse lors de l’accès (On-Access Scan), désactivez l’option de protection contre le débordement de la mémoire tampon (Buffer Overflow Protection) de la Console McAfee VirusScan.

Si une fonction n’est pas disponible, le nom de la commande dans le menu et le bouton de barre d’outils correspondant ne sont pas disponibles. Dans Document Security Extension for Microsoft Office, lorsque vous placez le pointeur de la souris sur une commande ou un bouton, une info-bulle indique que la commande est rendue indisponible par Document Security.

### Ouverture des fichiers protégés par une stratégie {#opening-policy-protected-files}

Vous pouvez ouvrir des fichiers protégés par une stratégie en utilisant les mêmes méthodes que celles utilisées pour ouvrir tout autre fichier. Si vous n’êtes pas encore connecté à Document Security, vous êtes invité à le faire, sauf si vous n’êtes pas connecté à Internet et que vous pouvez ouvrir le fichier hors connexion. Si vous annulez le processus de connexion, l’accès est refusé.

Si vous n’êtes pas autorisé à ouvrir le fichier, vous êtes informé que l’accès est refusé. Si les privilèges d’accès aux fichiers ont été révoqués, vous pouvez également être redirigé vers une version mise à jour du fichier si celle-ci est disponible. Pour obtenir une assistance supplémentaire si vous ne pouvez pas ouvrir un fichier protégé par une stratégie, contactez l’éditeur de fichiers.

Lorsqu’un fichier protégé est ouvert, le texte de la barre de titre qui suit le nom du fichier indique que le fichier est protégé par AEM Document Security.

Lors de l’ouverture d’un document protégé dans Document Security Extension for Microsoft Office à partir de SharePoint Server, assurez-vous que le programme Microsoft Office associé au type de fichier, par exemple Microsoft Word, Microsoft Excel ou Microsoft PowerPoint, est ouvert. Si vous essayez d’ouvrir le fichier sans accéder à l’application associée, le document risque de ne pas s’ouvrir et un message d’erreur indiquant que vous devez installer le plug-in approprié s’affiche. Outre l’ouverture de l’application requise, il est recommandé de vider le dossier de cache avant d’ouvrir un document protégé dans Document Security Extension for Microsoft Office à partir de SharePoint Server. De même, lorsque vous ouvrez un document protégé depuis SharePoint Server, toutes les autorisations du document sont désactivées, quelle que soit la stratégie appliquée.

Selon la méthode d’authentification mise en œuvre sur Document Security, vous pouvez être invité à choisir la méthode d’authentification lorsque vous ouvrez un document protégé. Si Document Security prend en charge plusieurs méthodes d’authentification, les options d’authentification vous sont présentées. Par exemple, si le serveur Document Security fournit à la fois le nom d’utilisateur/mot de passe et l’authentification par certificat, vous pouvez choisir la méthode d’authentification appropriée. Si l’authentification par certificat est activée, vous êtes invité à utiliser le certificat que vous avez reçu et installé.

L’expérience de l’utilisateur lors de l’ouverture de fichiers protégés dépend de la configuration de l’authentification mutuelle sur le serveur. Si un seul certificat client valide est installé, aucune boîte de dialogue d’authentification n’apparaît et les fichiers s’ouvrent correctement. Cependant, si plusieurs certificats clients sont installés sur un ordinateur, une boîte de dialogue d’authentification s’affiche. L’utilisateur doit choisir un certificat valide pour ouvrir le fichier protégé.

### Suppression de la protection de stratégie d’un fichier {#removing-policy-protection-from-a-file}

Si vous en avez l’autorisation, vous pouvez supprimer la protection de stratégie des fichiers que vous avez protégés. Dans ce cas, le fichier n’est plus protégé par Document Security.

1. Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Supprimer**.

   Si vous n’avez pas encore indiqué d’informations de connexion à Document Security, une boîte de dialogue vous invite à saisir votre nom d’utilisateur et votre mot de passe.

>[!NOTE]
>
>Si vous ne pouvez pas supprimer une stratégie d’un fichier que vous avez protégé, contactez un administrateur Document Security.

### Affichage des paramètres de protection {#viewing-security-settings}

Vous pouvez consulter les autorisations délivrées pour le fichier ouvert concernant l’impression, la copie, les modifications et l’accès hors connexion, ainsi que la période de validité du fichier.

Dans Document Security Extension for Microsoft Office 2010, la section Etat de la protection de l’onglet Document Security affiche vos autorisations pour le fichier.

Procédez comme suit :

* Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez un élément dans la section **Etat de la protection**.

### Enregistrement des documents lorsque l’application automatique de la stratégie est activée {#saving-documents-when-auto-apply-policy-is-enabled}

Si votre administrateur a activé la fonctionnalité d’application automatique de la stratégie, tout document créé ou modifié sera automatiquement protégé lors de son enregistrement.

Cette application automatique étant activée, Document Security Extension for Microsoft Office vous invite à vous connecter au serveur Document Security. Vous devrez fournir votre nom d’utilisateur et votre mot de passe pour être authentifié par le serveur. Si vous avez fourni les informations de connexion appropriées, le document est enregistré et protégé.

>[!NOTE]
>
>Si vous ne pouvez pas vous connecter à Document Security, le document peut être enregistré ou non. Cela dépend de la manière dont votre administrateur a configuré la stratégie d’application automatique. Vérifiez avec l’administrateur comment les documents sont traités dans cette situation.

### Synchronisation en vue de l’accès hors connexion {#synchronizing-for-offline-access}

Les stratégies vous permettent d’ouvrir des fichiers lorsque vous êtes hors ligne et que vous n’êtes pas connecté à Document Security. Vous devez vous être connecté auparavant à Document Security pour établir vos informations d’identification avec le serveur et pouvoir ainsi travailler hors connexion. Si vous envisagez de travailler avec des fichiers hors ligne, il est préférable de vous synchroniser avec Document Security avant de vous déconnecter. Vous pourrez ainsi vous assurer que les paramètres de stratégie de vos fichiers sont à jour avec le serveur. Il est recommandé d’ouvrir également le fichier en ligne une fois avant de l’ouvrir hors connexion. Si vous n’ouvrez pas le fichier à une reprise en ligne ou si vous ne le synchronisez pas avec le serveur, il est possible que vous puissiez tout de même utiliser des fichiers protégés par une stratégie alors que vous êtes hors ligne. Toutefois, la période d’ouverture hors connexion ne doit pas avoir expiré et les paramètres de stratégie du fichier ne doivent pas avoir été modifiés depuis la dernière synchronisation manuelle ou automatique avec le serveur.

Procédez comme suit :

* Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez l’option **Synchronisation hors connexion**.

   ***Remarque** : Le bouton de synchronisation hors connexion est disponible, même lorsque l’utilisateur ne dispose pas d’une autorisation hors connexion pour le document. Toutefois, ce bouton est inopérant. *

### Utilisation des filigranes dynamiques {#working-with-dynamic-watermarks}

Document Security Extension for Microsoft Office prend en charge l’inclusion de filigranes dynamiques basés sur du texte dans les documents protégés par une stratégie. Un filigrane dynamique peut inclure des informations qui peuvent changer, telles que la date, l’heure, le nom d’utilisateur ou le nom de la stratégie. Si un utilisateur imprime un fichier protégé par une stratégie et que ce fichier contient un filigrane dynamique et l’autorisation d’impression, le filigrane s’affiche dans la sortie.

Document Security Extension ne prend pas en charge les fonctions de filigrane enrichies telles que les filigranes PDF, les éléments multiples d’un filigrane, les options de formatage de texte et la plage de pages.

Vous pouvez créer un filigrane dynamique en accédant aux pages Web Document Security. Pour plus d’informations sur la création de filigranes dynamiques dans un document protégé par stratégie, consultez [Aide pour l’utilisateur final de Document Security](http://www.adobe.com/go/learn_lc_euRightsMgmt_11_fr).

Document Security Extension for Microsoft Office prend en charge les fonctionnalités de filigrane suivantes :

<table>
 <thead>
  <tr>
   <th><p>Options des filigranes de Document Security</p></th>
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

### Utilisation des pages web de Document Security {#opening-the-document-security-web-pages}

Vous pouvez ouvrir les pages web de Document Security pour créer et mettre à jour vos stratégies d’utilisateur, mais aussi pour afficher les informations d’état et d’audit sur vos fichiers protégés par une stratégie. Vous pouvez également utiliser les pages web de Document Security pour modifier des stratégies ou révoquer l’accès à un fichier protégé par une stratégie.

Pour ouvrir les pages web Document Security, dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Création et gestion des stratégies**. Si vous n’avez pas encore fourni vos informations de connexion, le navigateur s’ouvre à la page de connexion au serveur.

### Modification des stratégies {#changing-policies}

Si vous disposez d’autorisations, généralement en tant qu’administrateur de Document Security ou en tant qu’éditeur de fichiers, vous pouvez ultérieurement appliquer une autre stratégie à un fichier ou modifier les paramètres de la stratégie appliquée.

Pour modifier les paramètres d’une stratégie, utilisez les pages web Document Security.

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft Office 2010 ou 2013, dans l’onglet **Document Security**, sélectionnez **Sécuriser > Modifier la protection**.

1. Dans la liste, sélectionnez une stratégie, puis cliquez sur **Appliquer**.

### Révocation des privilèges d’accès aux fichiers {#revoking-file-access-privileges}

Vous pouvez révoquer la capacité d’ouvrir les fichiers que vous avez protégés. Lorsque vous révoquez les privilèges d’accès à un fichier, vous pouvez également spécifier le message qui s’affiche pour toute personne qui tente d’ouvrir le fichier, ainsi que l’URL vers une version mise à jour du fichier si vous le remplacez par une copie révisée.

1. Procédez comme suit :

   * Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Révoquer**.

   Les pages web Document Security s’ouvrent sur la page Révoquer les documents.

1. Spécifiez un message à afficher et, le cas échéant, une URL pour la version mise à jour. Cliquez ensuite sur **OK**.

Pour plus d’informations sur la révocation des privilèges d’accès aux fichiers, consultez [Aide pour l’utilisateur final de Document Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Les privilèges d’accès peuvent être rétablis via les pages Web Document Security.

### Affichage de l’historique d’audit des fichiers {#viewing-the-file-audit-history}

Document Security peut enregistrer l’historique des audits pour les fichiers protégés par une stratégie afin que vous puissiez contrôler les actions des utilisateurs sur vos fichiers.

Les événements contrôlés pour les fichiers Word, Excel et PowerPoint sont les suivants :

**Sécurisation d’un nouveau document** Politique appliquée à un fichier

**Affichage d’un document** Fichier ouvert

**Fermeture d’un document** Fichier fermé

**Révocation d’un document** Privilèges d’accès supprimés pour le fichier

**Annulation de la révocation du document** Privilèges d’accès renvoyés au fichier

**Modification du document** Fichier modifié et enregistré localement

**Impression en haute résolution** Fichier imprimé

**Gestionnaire de modification de la protection** Protection de la politique supprimée du fichier

**Changement de stratégie concernant le document** Nouvelle stratégie appliquée au fichier à partir des pages web Document Security

### Affichage de l’historique des contrôles d’un fichier {#view-the-audit-history-for-a-file}

Dans Document Security Extension for Microsoft Office 2010 et 2013, dans l’onglet **Document Security**, sélectionnez **Historique des contrôles**.

Les pages Web Document Security s’ouvrent à la page Événements, qui répertorie les événements contrôlés du fichier ouvert.

### Fonctionnalités restreintes dans Microsoft Office {#microsoft-office-restricted-features}

Pour protéger votre propriété intellectuelle, certaines fonctionnalités de Microsoft Office ne sont pas disponibles lorsqu’un fichier protégé par une stratégie est ouvert. La liste des fonctionnalités indisponibles dépend des autorisations accordées à l’utilisateur actuel. Certaines fonctionnalités ne sont disponibles que pour un fichier protégé, tandis que d’autres ne le sont que pour tous les fichiers lorsque vous êtes dans une session protégée. En règle générale, vous êtes dans une session protégée entre l’ouverture d’un fichier protégé par une stratégie et la fermeture de l’application ou l’expiration de la session.

La plupart des stratégies accordent des autorisations complètes à l’éditeur de fichiers. Il est possible que d’autres utilisateurs remarquent des restrictions supplémentaires relatives aux fonctions.

Si une fonction n’est pas disponible, le nom de la commande dans le menu et le bouton correspondant de la barre d’outils apparaissent en grisé.

>[!NOTE]
>
>L’application d’une stratégie à un fichier contenant un lien vers un fichier incorporé n’applique pas la stratégie au fichier lié. Document Security for Microsoft Office n’étend pas la protection aux fichiers liés.

* Les fichiers Word, Excel et PowerPoint protégés par une stratégie ne peuvent pas s’ouvrir dans une fenêtre du navigateur Internet Explorer.
* Les utilisateurs qui n’ont obtenu que l’autorisation Modifier ne peuvent pas copier du contenu dans un fichier issu d’une autre application à l’aide du presse-papiers Windows. Les utilisateurs peuvent copier du contenu dans des fichiers en activant l’option Presse-papiers de Microsoft Office.
* L’ouverture d’un fichier protégé par une stratégie dans Microsoft Office rend la clé d’écran d’impression indisponible jusqu’à ce que vous fermiez l’application ou que la session expire.
* Document Security for Microsoft Office ne prend pas en charge le protocole WebDAV (Web-based Distributed Authoring and Versioning). Dans la plupart des cas, vous ne pouvez pas ouvrir un fichier protégé par une stratégie depuis un dossier WebDAV. Si vous pouvez ouvrir un fichier protégé par une stratégie, vous n’avez pas l’autorisation d’enregistrer, d’imprimer, de modifier ni de copier ce fichier.

La protection générale appliquée aux fichiers protégés par une stratégie comprend les restrictions suivantes :

Au cours d’une session protégée, il est possible que de nombreuses fonctionnalités courantes soient restreintes dans Word, Excel et PowerPoint.

En cas d’ouverture d’un fichier protégé par une stratégie qui ne permet pas à l’utilisateur d’apporter des modifications, les commandes qui modifient le fichier de manière arbitraire ne sont pas disponibles. Seules sont disponibles les commandes qui ouvrent ou créent des documents et modifient les préférences de l’application.

#### Restrictions de Word 2010 et Word 2013 {#word-2010-and-word-2013-restrictions}

Dans Word, l’ouverture d’un fichier protégé par une stratégie rend inaccessible l’enregistrement des informations de récupération automatique de fichiers jusqu’à ce que vous fermiez et redémarriez Word. En outre, les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations suivantes :

**Fichier > Nouveau > Nouveau à partir d’un fichier existant** Disponible, mais il est impossible d’enregistrer les fichiers créés à l’aide de cette commande alors qu’un fichier protégé par une stratégie est ouvert. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier > Enregistrer** Restreinte par l’autorisation Modifier.

**Fichier > Enregistrer sous** Toutes les options sont restreintes par l’autorisation Modifier.

**Fichier > Imprimer** Toutes les options sont restreintes par l’autorisation Impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Fichier > Enregistrer et Envoyer** Toutes les options sont indisponibles pendant une session protégée.

**Fichier > Infos > Protéger le document >
Chiffrer avec mot de passe, Ajouter une signature numérique, Marquer comme final, Restreindre l’autorisation par les personnes** Non disponible pendant une session protégée.

**Fichier > Workflows** Non disponible pendant une session protégée.

***Remarque ** : La fonction de démarrage d’un workflow à partir des versions Microsoft Office 2010 de Word, Excel et PowerPoint est disponible uniquement dans les suites Office Professional Plus 2010, Office Enterprise 2010 et Office Ultimate 2010, ainsi que dans les versions Office 2010 autonomes de ces programmes.*

**Billet de blog > Publier** Non disponible pendant une session protégée.

**Fichier > Serveur > Menu Tâches du serveur de fichiers** Non disponible pendant une session protégée.

**Accueil > Presse-papiers > Copier** Restreinte par l’autorisation Copier. Si la copie n’est pas autorisée, le contenu copié ne peut pas être collé dans un autre fichier ou dans le presse-papiers d’Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers > Coller** Restreinte par l’autorisation Modifier.

**Accueil > Presse-papiers > Collage spécial** Restreinte par l’autorisation Modifier.

**Insérer > Texte > Objet** Non disponible pendant une session protégée. Il est impossible d’insérer à tout moment des fichiers protégés par une stratégie.

**Publipostage** La plupart des options de cet onglet ne sont pas disponibles pendant une session protégée.

**Révision > Vérification > Recherche** Restreinte par l’autorisation Copier. Non disponible si la copie n’est pas autorisée.

**Révision > Vérification > Dictionnaire des synonymes** Restreinte par l’autorisation Copier. Non disponible si la copie n’est pas autorisée.

**Révision > Langue > Traduire > Traduire le document** Activé avec l’autorisation Copier.

**Révision > Langue > Traduire > Traduire le texte sélectionné** Activé avec l’autorisation Copier.

**Révision > Langue > Traduire > Mini-traducteur** Activé avec l’autorisation Copier.

**Révision > Comparer > Comparer** Non disponible pendant une session protégée. Les fichiers protégés par une stratégie ne peuvent être comparés à aucun moment.

**Révision > Protéger > Bloquer des auteurs** Non disponible pendant une session protégée.

**Révision > Protéger > Restreindre la modification** Non disponible pendant une session protégée.

**Affichage > Macros** Certaines macros sont restreintes par l’autorisation Copier et ne sont pas disponibles sauf si la copie est autorisée.

**Modules complémentaires** Ne peuvent pas être ajoutés ni supprimés pendant une session protégée.

**Collaboration en ligne** Non disponible pendant une session protégée.

**Document principal et sous-documents** Les sous-documents sont régis par la stratégie des documents maîtres lorsqu’ils sont ouverts dans un document maître. S’ils sont ouverts séparément, les sous-documents ne peuvent pas être imprimés, copiés ni modifiés.

**Refaire la synthèse** Non disponible pendant une session protégée.

**Images (et toutes les commandes associées)** Non disponibles pendant une session protégée.

**Panneau de documents** Non disponible pendant une session protégée.

**Développeur > Modèle de document** Non disponible pendant une session protégée. Pour accéder à cette commande, choisissez Fichier > Options > Personnaliser > Onglet Développeur > Modèles > Modèle de Document.

**Mode plan > Document principal > Créer un sous-document,
Insérer un sous-document** Non disponible pendant une session protégée.

#### Restrictions dans Excel 2010 et Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations suivantes :

**Fichier > Nouveau > Nouveau à partir d’un fichier existant** Disponible, mais il est impossible d’enregistrer les fichiers créés à l’aide de cette commande au cours d’une session protégée. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier > Enregistrer, Enregistrer sous** Restreinte par l’autorisation Modifier.

**Fichier > Enregistrer sous > PDF** Non disponible pendant une session protégée.

**Fichier > Imprimer** Restreinte par l’autorisation d’impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Fichier > Infos > Protéger le document** Non disponible pendant une session protégée.

**Fichier > Infos > Protéger le classeur** Non disponible pendant une session protégée.

**Fichier > Enregistrer et Envoyer** Non disponible pendant une session protégée.

**Fichier > Options > Modules complémentaires** Ne peuvent pas être ajoutés ni supprimés pendant une session protégée.

**Fichier > Workflows** Non disponible pendant une session protégée.

***Remarque ** : La fonction de démarrage d’un workflow à partir des versions Microsoft Office 2010 de Word, Excel et PowerPoint est disponible uniquement dans les suites Office Professional Plus 2010, Office Enterprise 2010 et Office Ultimate 2010, ainsi que dans les versions Office 2010 autonomes de ces programmes.*

**Fichier > Serveur > Menu Tâches du serveur de fichiers** Non disponible pendant une session protégée.

**Accueil > Presse-papiers > Copier** Restreinte par l’autorisation Copier. Si la copie n’est pas autorisée, le contenu copié ne peut pas être collé dans un autre fichier ou dans le presse-papiers de Microsoft Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers > Coller** Restreinte par l’autorisation Modifier.

**Accueil > Presse-papiers > Collage spécial** Restreinte par l’autorisation Modifier.

**Accueil > Cellules > Format > Déplacer ou copier une feuille** Non disponible pendant une session protégée.

**Accueil > Cellules > Insérer > Insérer une feuille** Non disponible pendant une session protégée.

**Accueil > Cellules > Supprimer > Supprimer une feuille** Non disponible pendant une session protégée.

**Accueil > Édition > Remplir > Sur une feuille de calcul** Restreinte par l’autorisation Modifier.

**Insérer > Tableaux > Tableau** Restreinte par l’autorisation Modifier.

**Insérer > Tableaux > Tableaux croisés dynamiques** Il est impossible de sélectionner des fichiers protégés par une stratégie de tableau dans l’Assistant de création.

**Insérer > Texte > Objet** Non disponible pendant une session protégée. Il est impossible d’insérer à tout moment des fichiers protégés par une stratégie.

**Insérer > Texte > En-tête et pied de page** Restreinte par l’autorisation Modifier. Non disponible pour un document protégé par une stratégie.

**Données > Obtenir des données externes** Il est impossible d’importer des données à partir de fichiers protégés par une stratégie.

**Données > Plan > Sous-totaux** Restreinte par l’autorisation Modifier.

**Données > Outils de données > Validation des données** Restreinte par l’autorisation Modifier.

**Révision > Vérification > Recherche** Restreinte par l’autorisation Copier.

**Révision > Vérification > Dictionnaire des synonymes** Restreinte par l’autorisation Copier.

**Révision > Langue > Traduire** Restreinte par l’autorisation Copier.

**Révision > Changements > Protéger la feuille** Non disponible pendant une session protégée.

**Révision > Modifications > Protéger le classeur** Non disponible pendant une session protégée.

**Révision > Changements > Partager le classeur** Non disponible pendant une session protégée.

**Révision > Changements > Protéger et partager le classeur** Non disponible pendant une session protégée.

**Révision > Modifications > Permettre aux utilisateurs de modifier des plages** Non disponible pendant une session protégée.

**Révision > Modifications > Suivi des modifications > Mettre les modifications en surbrillance** Non disponible pour un fichier protégé par une stratégie qui contient un filigrane dynamique.

**Affichage > Macros** Restreinte par l’autorisation Modifier.

**Affichage > Enregistrer l’espace de travail** La commande ne fonctionne pas.

**Développeur > XML > Kits d’extension** Certaines macros sont restreintes par l’autorisation Copier et ne sont pas disponibles, sauf si la copie est autorisée.

**Formules > Audit de formules > Vérification des erreurs** Restreinte par l’autorisation Modifier. Non disponible sauf si la modification est autorisée.

**Collaboration en ligne** Non disponible pendant une session protégée.

**Enregistrer les informations de récupération automatique** Indisponible pendant une session protégée.

***Remarque ** : Si vous tentez de modifier une cellule dans un fichier protégé par une stratégie pour lequel vous n’êtes pas autorisé à effectuer des modifications, Excel affiche un message d’avertissement pour une opération incorrecte et vous indique que vous devez ôter la protection du fichier à l’aide de la commande Ôter la protection de la feuille. L’utilisation de cette commande ne supprime pas la protection de stratégie du fichier.*

#### Restrictions dans PowerPoint 2010 et PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Les fonctionnalités répertoriées ci-dessous sont restreintes dans les situations suivantes :

**Fichier > Nouveau > Nouveau à partir d’un fichier existant** Disponible, mais il est impossible d’enregistrer les fichiers créés à l’aide de cette commande au cours d’une session protégée. Le contenu du nouveau fichier ne peut pas être copié dans un autre fichier.

**Fichier > Enregistrer** Restreinte par l’autorisation Modifier.

**Fichier > Enregistrer sous** Toutes les options sont restreintes par l’autorisation Modifier.

**Fichier > Imprimer** Toutes les options sont restreintes par l’autorisation Impression. Non disponible, sauf si la stratégie autorise l’impression haute résolution.

**Fichier > Enregistrer et Envoyer** Non disponible pendant une session protégée.

**Fichier > Infos > Protéger la présentation >
Chiffrer avec mot de passe, Ajouter une signature numérique, Marquer comme final, Restreindre l’autorisation par les personnes** Non disponible pendant une session protégée.

**Fichier > Options PowerPoint > Enregistrer les informations de récupération automatique** Indisponible pendant une session protégée.

**Fichier > Serveur > Menu Tâches du serveur de fichiers** Non disponible pendant une session protégée.

**Accueil > Presse-papiers > Copier** Restreinte par l’autorisation Copier. Si la copie n’est pas autorisée, le contenu copié ne peut pas être collé dans le document, dans un autre fichier ou dans le presse-papiers d’Office. Le contenu peut être copié dans le fichier protégé si l’utilisateur dispose de l’autorisation de modification.

**Accueil > Presse-papiers > Coller** Restreinte par l’autorisation Modifier. Si la copie n’est pas autorisée, le contenu copié ne peut pas être collé dans le document.

**Accueil > Presse-papiers > Collage spécial** Restreinte par l’autorisation Modifier.

**Accueil > Diapositives > Nouvelles diapositives > Diapositives à partir d’un plan, réutiliser les diapositives** Non disponible pendant une session protégée.

**Insérer > Texte > Objet** Non disponible pendant une session protégée. Il est impossible d’insérer à tout moment des fichiers protégés par une stratégie.

**Création > Arrière-plan > Styles d’arrière-plan, Masquer les graphiques d’arrière-plan, Mise en forme de l’arrière-plan** Non disponible pour un fichier protégé par une stratégie qui contient un filigrane dynamique.

**Diaporama > Configurer > Enregistrer le diaporama** Restreinte par l’autorisation de modification.

**Révision > Vérification > Dictionnaire des synonymes** Restreinte par l’autorisation Copier.

**Révision > Langue > Traduire** Restreinte par l’autorisation Copier.

**Révision > Langue > Traduire > Mini-traducteur** Activé avec l’autorisation Copier.

**Affichage > Vues de présentation > Diaporama** Restreinte par l’autorisation Modifier. Si les modifications ne sont pas autorisées, les diaporamas ne peuvent pas être affichés si le fichier a été modifié.

**Affichage > Macros** Certaines macros sont restreintes par l’autorisation Copier et ne sont pas disponibles sauf si la copie est autorisée.

**Modules complémentaires** Ne peuvent pas être ajoutés ni supprimés pendant une session protégée.

**Collaboration en ligne** Non disponible pendant une session protégée.

## Utilisation de fournisseurs d’authentification tiers {#use-third-party-authentication-providers}

Vous pouvez utiliser des fournisseurs d’authentification tiers avec AEM Forms Document Security. Ces fournisseurs d’authentification vous permettent d’ajouter une couche supplémentaire d’accès aux documents protégés. AEM Forms Document Security prend en charge les processus d’authentification étendue suivants :

* Authentification étendue à l’aide de l’URL d’AEM Forms par défaut
* Authentification étendue à l’aide d’une URL personnalisée
* Processus d’authentification étendue par défaut avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Processus d’authentification étendue personnalisée avec les fournisseurs tiers d’identité configurés sur le serveur AEM Forms on JEE
* Authentification étendue à l’aide d’une page personnalisée pour les listes d’authentification SAML

## Glossaire {#glossary}

Pour plus d’informations sur la terminologie LiveCycle et AEM forms on JEE, consultez le [Glossaire](http://www.adobe.com/go/learn_aemforms_designer_65).

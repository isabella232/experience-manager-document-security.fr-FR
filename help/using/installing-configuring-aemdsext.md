---
title: Installation et configuration d’AEM Document Security Extension for Microsoft Office
description: Ce document vous guide pour l’installation et la configuration d’Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: ht
source-wordcount: '2775'
ht-degree: 100%

---

# Installation et configuration d’AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Ce document vous guide pour l’installation et la configuration d’Adobe Experience Manager Document Security Extension for Microsoft Office.

Ce document contient des informations relatives aux tâches suivantes :

* Installation de Document Security Extension for Microsoft Office
* Préconfiguration de l’installation pour pointer sur LiveCycle Rights Management ES2 ou versions ultérieures ou le module complémentaire Document Security pour AEM 6.0 Forms ou versions ultérieures.
* Configuration de l’application automatique de la politique par défaut

## Avant l’installation {#before-you-install}

Avant d’installer l’extension Document Security pour Microsoft Office, assurez-vous que vous remplissez les conditions suivantes :

* Vous avez lu les [Notes de mise à jour](document-security-extension-release-notes.md).
* Microsoft Office est activé. la boîte de dialogue d’activation n’apparaît pas lors de l’ouverture des applications Microsoft Office.
* les Service Packs les plus récents pour Microsoft Windows et Microsoft Office sont installés.
* Si vous installez Document Security pour Microsoft Office dans une langue non prise en charge, lancez au moins une fois l’application Office.

>[!NOTE]
>
>N’installez pas le logiciel dans un dossier dont le nom contient des caractères codés sur deux octets. Dans le cas contraire, le menu Document Security d’AEM ne s’affiche pas dans Microsoft Office.

>[!NOTE]
>
>L’installation d’une version en 32 bits de Document Security Extension sur un système d’exploitation en 64 bits est prise en charge mais l’opposé n’est pas pris en charge. Vous ne pouvez pas installer la version 64 bits de l’extension Document Security for Microsoft Office sur un système d’exploitation 32 bits.

### Désactivation de McAfee VirusScan {#disable-mcafee-virusscan}

Pour garantir le démarrage correct des applications Office sur un ordinateur doté de Document Security Extension et de McAfee VirusScan avec activation de l’option d’analyse lors de l’accès (On-Access Scan), désactivez l’option de protection contre le débordement de la mémoire tampon (Buffer Overflow Protection) de la Console McAfee VirusScan.

### Désinstallation des plug-ins tiers {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office ne prend pas en charge les modules externes tiers pour les applications Microsoft Office. Comme cette extension est en conflit avec les plug-ins tiers, désinstallez les plug-ins des fournisseurs autres qu’Adobe dans Microsoft Office avant d’installer Document Security pour Microsoft Office. Adobe ne prend pas en charge les applications Document Security pour Microsoft Office si des plug-ins tiers sont installés.

## Configuration requise {#system-requirements}

### Client Document Security Extension {#document-security-extension-client}

Vérifiez les configurations minimales suivantes sur lesquelles vous souhaitez installer Document Security Extension :

* Versions 32 ou 64 bits de Microsoft Windows 7 ou Windows 10 en anglais, français, allemand, japonais, italien, espagnol, portugais brésilien, coréen, chinois simplifié ou traditionnel.
  **Remarque :** *Document Security Extension for Microsoft Office est également prévu pour fonctionner sur des appareils Microsoft Surface.*

* Versions 32 ou 64 bits de Microsoft Office 2013, 2016, 2019 et applications de bureau Microsoft Office installées avec Office 365 en anglais, français, allemand, japonais, italien, espagnol, portugais brésilien, coréen, chinois simplifié ou traditionnel.

  **Remarque** : *l’extension Document Security d’AEM pour Microsoft Office ne prend pas en charge les plug-ins tiers pour les applications Microsoft Office. Comme cette extension peut entrer en conflit avec des plug-ins tiers, tous les plug-ins de fournisseurs autres qu’Adobe pour les applications Microsoft Office doivent être désinstallés avant de procéder à l’installation de Document Security pour Microsoft Office. Adobe ne prend pas en charge les extensions Document Security pour les applications Microsoft Office avec des plug-ins tiers installés.*

* Processeur 1,3 GHz ou supérieur
* 2 Go de RAM
* 100 Mo d’espace disque disponible

### Document Security {#document-security}

Pour utiliser Document Security Extension, vous devez pouvoir vous connecter à Adobe LiveCycle Rights Management ES2 et versions ultérieures ou au module complémentaire Document Security pour AEM forms 6.0 ou versions ultérieures.

## Installation de Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

Vous pouvez télécharger le programme d’installation à partir de la [page des téléchargements](download-installer.md). Vous ne pouvez pas personnaliser directement le fichier exécutable du programme d’installation, mais il peut être installé de manière interactive ou en mode silencieux. Pour installer le logiciel, connectez-vous à Windows en tant qu’administrateur.

Des programmes d’installation distincts sont disponibles pour les versions 32 bits et 64 bits de Microsoft Office. Pour la version 32 bits de Microsoft Office, téléchargez DocumentSecurityExtensionforMicrosoftOffice.exe. Pour la version 64 bits de Microsoft Office, téléchargez DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>Ce document utilise un fichier d’installation 32 bits (DocumentSecurityExtensionforMicrosoftOffice.exe) afin d’expliquer diverses commandes et options. Si vous utilisez une version 64 bits de Microsoft Office, utilisez le fichier d’installation 64 bits (DocumentSecurityExtensionforMicrosoftOffice64.exe) pour réaliser les opérations indiquées dans ce document.

### Installation en mode silencieux {#install-in-silent-mode}

Utilisez un utilitaire d’extraction de fichier, tel que WinZip, pour extraire `DocumentSecurityExtensionforMicrosoftOffice.exe` du fichier d’installation. Ouvrez l’invite de commande, accédez au dossier contenant le fichier d’installation, puis saisissez le texte suivant :

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

Le programme d’installation est également disponible sous la forme d’un fichier MSI, qui peut être utilisé pour la personnalisation.

### Installation d’un fichier MSI en mode silencieux {#install-an-msi-file-in-silent-mode}

1. Utilisez un utilitaire d’extraction de fichier, tel que WinZip, pour extraire `DocumentSecurityExtensionforMicrosoftOffice.msi` du fichier ZIP.

1. Ouvrez l’invite de commande, accédez au dossier contenant le fichier MSI, puis saisissez le texte suivant :

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Préconfiguration du programme d’installation pour la connexion à Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

Vous pouvez préconfigurer le programme d’installation de Document Security Extension for Microsoft Office pour qu’il pointe vers un LiveCycle ou un serveur AEM. Ainsi, les utilisateurs qui installent Document Security Extension for Microsoft Office peuvent utiliser les fonctionnalités sans configurer de connexion. En outre, ces utilisateurs peuvent ouvrir des documents protégés sans configuration. Toutefois, ils ne peuvent pas protéger les nouveaux documents tant qu’ils n’ont pas configuré le client pour qu’il utilise un serveur particulier.

Les étapes suivantes décrivent comment créer et configurer un fichier MSI. Ce fichier MSI contient les valeurs de registre requises pour préconfigurer le programme d’installation de Document Security Extension for Microsoft Office sur le LiveCycle ou le serveur AEM installé dans votre entreprise.

### Conditions préalables pour la personnalisation du programme d’installation {#prerequisites-for-customizing-the-installer}

Utilisez l’éditeur de base de données Orca pour personnaliser le programme d’installation. Les étapes suivantes décrivent comment créer un fichier MSI personnalisé en modifiant une copie du fichier d’installation MSI à l’aide de l’éditeur de base de données Orca. Orca est disponible dans le cadre du SDK Windows pour Windows Server 2008 et .NET Framework 3.5.

<!--

For more information about how to edit Microsoft Windows® Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>Il est recommandé d’effectuer une sauvegarde complète de tous les fichiers d’installation avant de créer le fichier MSI personnalisé.

#### Installation d’Orca {#install-orca}

1. Téléchargez le SDK Windows pour Windows Server 2008 et .NET Framework 3.5.
1. Double-cliquez sur le fichier Orca.msi dans le dossier \Microsoft SDK\bin.

   Vous avez également besoin de la variante MSI du fichier d’installation. Contactez l’assistance d’Adobe pour recevoir la dernière version du programme d’installation MSI.

   >[!NOTE]
   >
   >Fermez toujours le fichier DocumentSecurityExtensionforMicrosoftOffice.msi avant d’exécuter le programme d’installation. Vous ne pouvez pas exécuter le programme d’installation si Orca utilise le fichier MSI.

### Création et configuration du fichier MSI {#create-and-configure-the-msi-file}

1. Cliquez sur **[!UICONTROL Démarrer > Programmes > Orca]**.

1. Cliquez sur **[!UICONTROL Fichier > Ouvrir]**, puis accédez au fichier `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Sélectionnez Property dans la liste des tables (sur le côté gauche).

1. Modifiez les valeurs de nom des clés suivantes en fonction de l’installation de Rights Management ou Document Security de votre entreprise.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nom de la </strong><strong></strong><strong>clé</strong></p> </td>
   <td><p><strong>Description</strong></p> </td>
   <td><p><strong>Valeur de la </strong><strong></strong><strong>clé par défaut</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Nom d’affichage.</p> </td>
   <td><p>Serveur par défaut</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>URL du serveur hôte.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Sélectionnez Registry dans la liste des tables (sur le côté gauche).

1. Modifiez la valeur de nom de la clé suivante.

   | **Nom de la clé** | **Description** | **Valeur de la clé par défaut** |
   |---|---|---|
   | `IsDefault` | Serveur APS par défaut. | Serveur par défaut |

1. Enregistrez le fichier modifié dans le répertoire contenant le programme d’installation MSI d’origine.

   >[!NOTE]
   >
   >Il est courant d’utiliser le même nom de fichier que celui du fichier MSI d’origine (par exemple, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configuration de l’application automatique d’une politique par défaut {#configuring-automatic-application-of-a-default-policy}

Dans le cadre de la configuration, vous pouvez configurer l’application automatique d’une politique par défaut afin que Document Security Extension for Microsoft Office protège chaque document enregistré.

Vous pouvez spécifier l’une des options suivantes :

* Protéger tous les documents à l’aide d’une politique par défaut.
* Permettre aux utilisateurs d’enregistrer un fichier dans un format non protégé lorsqu’ils ne peuvent pas se connecter au serveur. Cette flexibilité permet de tenir compte des cas où les utilisateurs créent des documents alors qu’ils sont déconnectés du réseau (par exemple, lorsqu’ils sont dans un avion).

Après avoir activé la fonction d’application automatique de la politique, le document est protégé par la politique par défaut dans les cas suivants :

* L’utilisateur modifie et enregistre un document nouvellement créé.
* L’utilisateur modifie et enregistre un document non protégé.
* L’utilisateur lance une application qui s’ouvre avec un document par défaut, modifie, puis enregistre le document.

### Configuration de la fonction d’application automatique de la politique dans le fichier MSI  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Avant de commencer, préconfigurez le programme d’installation pour qu’il fasse référence au serveur LiveCycle ou AEM forms, comme décrit précédemment dans cet article.

1. Cliquez sur **[!UICONTROL Démarrer > Programmes > Orca]**.

1. Cliquez sur **[!UICONTROL Fichier > Ouvrir]**, puis accédez au fichier `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Sélectionnez Property dans la liste des tables (sur le côté gauche).

1. Modifiez les valeurs de nom des clés suivantes en fonction de l’installation de Rights Management ou Document Security de votre entreprise.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nom de la clé</strong></p> </td>
   <td><p><strong>Description</strong></p> </td>
   <td><p><strong>Valeur de la </strong><strong></strong><strong>clé par défaut</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Activez ou désactivez la fonction d’application automatique de la politique.</p> <p><code>1</code>: Activer</p> <p>0: Désactiver</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>GUID de la politique à utiliser lorsque de nouveaux documents sont enregistrés. S’applique à la fonction d’application automatique de la politique.</p> </td>
   <td><p>ID de politique hexadécimal visible sur le serveur RM</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>URL du serveur.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Numéro de port du serveur.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Détermine si des documents peuvent être créés sans la protection de Document Security, dans le cas où le client ne peut pas contacter le serveur pour protéger le document lors du premier enregistrement.</p> <p>1 : Autoriser les enregistrements non protégés </p> <p>0 : Empêcher la création de nouveaux documents lorsque le client ne peut pas contacter le serveur pour enregistrer le document.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` est utile lorsque vous souhaitez rappeler aux clients de protéger tous les documents sans les forcer à le faire. Cette option s’avère également précieuse lorsque vous savez que les utilisateurs et les utilisatrices créent des documents alors qu’ils sont déconnectés du réseau. Vous ne souhaitez pas les empêcher de créer et d’enregistrer des documents.

1. Enregistrez le fichier modifié dans le répertoire contenant le fichier MSI d’origine.

   >[!NOTE]
   >
   >Il est courant d’utiliser le même nom de fichier que celui du fichier MSI d’origine (par exemple, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Activation de la protection automatique des nouveaux documents {#enabling-automatic-protection-of-new-documents}

L’administrateur peut activer la possibilité de protéger automatiquement tout document enregistré par un utilisateur. L’administrateur configure la fonction d’application automatique de la politique dans le programme d’installation de Document Security Extension for Microsoft Office.

Si l’option Application automatique de la politique est activée, tous les documents enregistrés par l’utilisateur sont protégés par la politique par défaut. Cette action s’applique dans les cas suivants :

* Un utilisateur crée un document, le modifie et l’enregistre.
* Un utilisateur ouvre un document non protégé, le modifie et l’enregistre.

Pour plus d’informations sur la configuration de la fonction d’application automatique de la politique, voir [Configuration d’une application automatique de la politique par défaut](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Activation de l’interface utilisateur sans ruban {#enable-ribbon-less-user-interface}

Vous pouvez activer/désactiver l’interface utilisateur sans ruban en modifiant les paramètres dans le registre Windows. Effectuez les étapes suivantes pour mettre le registre à jour et activer l’interface utilisateur sans ruban :

1. Effectuez une sauvegarde du registre Windows avant d’apporter des modifications. Pour obtenir des instructions détaillées, consultez la section [Modifier le registre Windows](https://support.microsoft.com/fr-fr/kb/136393).
1. Dans l’éditeur du registre, accédez à HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 ou HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Créez une valeur (32 bits) Dword appelée **HidePluginUI**.

1. Définissez la valeur de la propriété **HidePluginUI** sur 1 pour activer l’interface utilisateur sans ruban.

1. Fermez l’éditeur du registre.

## Activation du filigrane pour impression dans Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

Vous pouvez modifier les paramètres du registre Windows afin que le filigrane dynamique coexiste avec les en-têtes et pieds de page existants. Les paramètres du registre rendent le filigrane disponible uniquement pendant l’impression. Effectuez la procédure suivante pour mettre à jour le registre et activer les filigranes lors de l’impression :

1. Effectuez une sauvegarde du registre Windows avant d’apporter des modifications. Pour obtenir des instructions détaillées, consultez la section [Modifier le registre Windows](https://support.microsoft.com/fr-fr/kb/136393).
1. Dans l’éditeur du registre, accédez à HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 ou HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Créez une clé de registre **WatermarkMode**.
1. Dans la clé de registre WatermarkMode, créez une valeur DWORD pour **WatermarkMode** et définissez la valeur DWORD de **WatermarkMode** sur **1**.

1. Fermez l’éditeur du registre.

>[!NOTE]
>
>Dans l’Explorateur Windows, vous pouvez créer un document Microsoft Excel à l’aide du menu Fichier ou du menu contextuel. Pour les documents créés avec des méthodes classiques, la date d’impression ne peut pas être récupérée ou modifiée. Il s’agit d’une limitation de Microsoft Excel. Les filigranes AEM Document Security dépendent de la date d’impression du document. Pour ces documents, le filigrane est donc ramené à une date antérieure. De plus, les en-têtes et pieds de page ne sont pas non plus conservés.

## Ajout d’une page personnalisée à un document {#coverpage}

Un utilisateur peut tenter d’ouvrir un document protégé sur un ordinateur sur lequel AEM Document Security for Microsoft Office n’est pas installé. Il est impossible d’ouvrir le document sur ces ordinateurs. Sur ces machines, vous pouvez afficher une page de garde contenant des instructions pour télécharger le module externe AEM Document Security for Microsoft Office et d’autres informations.

### Avant de configurer une page de garde {#before-you-configure-a-cover-page}

* Effectuez une sauvegarde du fichier CommonResources.dll. Le chemin par défaut est :

   * **(Pour la version 32 bits d’Office sur une machine en 32 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Pour la version 32 bits d’Office sur une machine en 64 bits)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Pour la version 64 bits d’Office sur une machine en 64 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Assurez-vous que Microsoft Visual Studio 2008 ou une version ultérieure est installé. Vous pouvez également utiliser n’importe quel autre utilitaire pour modifier les fichiers DLL.
* Procédez à l&#39;extraction de l’archive templates.zip. L’archive contient des modèles .xlsx, .docx et .pptx pour la page de garde. Utilisez uniquement les modèles fournis pour les types de fichiers .xlsx, .docx et .pptx. Vous pouvez créer vos propres modèles pour d’autres types de fichier. Personnalisez les modèles afin d’inclure des messages et des instructions personnalisés. Vous pouvez trouver templates.zip sur :

[Obtenir le fichier](assets/templates.zip)

### Structure du fichier CommonResources.dll {#structure-of-the-commonresources-dll-file}

Le fichier CommonResources.dll contient des informations sur les modèles de ressources. Il contient deux identifiants de nom : TEMPLATE_FILE et RT_MANIFEST. Pour activer une page de garde personnalisée, l’identifiant de nom TEMPLATE_FILE est modifié. L’identifiant de nom TEMPLATE_FILE possède six ressources :

<table>
 <tbody>
  <tr>
   <td><p><strong>Ressource</strong></p> </td>
   <td><p><strong>Représente </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Configuration du modèle en tant que page de garde {#configure-the-template-as-a-cover-page}

1. Ouvrez Microsoft Visual Studio. Recherchez et ouvrez le fichier CommonResources.dll pour le modifier.

   >[!NOTE]
   >
   >Si le fichier n’apparaît pas dans la fenêtre Solution Explorer, rouvrez le fichier en utilisant l’option Ouvrir avec. Sélectionnez l’éditeur Ressource comme éditeur.

1. Dans la fenêtre Solution Explorer, développez le répertoire TEMPLATE_FILE, et supprimez les ressources 101.

1. Ajoutez les ressources suivantes :

   1. Une fois un projet sélectionné dans l’explorateur de solutions, accédez au menu Projet et cliquez sur Propriétés.
   1. Sélectionnez l’onglet Ressources.
   1. Dans la barre d’outils Resource Designer, pointez le curseur de la souris sur Ajouter une ressource et cliquez sur la flèche. Pour le type de ressource, sélectionnez TEMPLATE_FILE, puis cliquez sur Importer.
   1. Dans la boîte de dialogue Ajouter un fichier existant aux ressources, sélectionnez le fichier Resource.xlsx, puis cliquez sur Ouvrir. Le fichier est ajouté au répertoire TEMPLATE_FILE.

   >[!NOTE]
   >
   >Assurez-vous que les paramètres de langue sont corrects. Supprimez la ressource dont la langue est neutre.

1. Répétez les étapes 2 et 3 pour tous les types de ressource.

   >[!NOTE]
   >
   >Ne supprimez pas et n’ajoutez pas des types de ressource de manière aléatoire. Après 101, configurez 102, etc.

### Personnalisation du fichier CommonResources.dll avec le programme d’installation d’AEM Document Security extension for Microsoft Office  {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

Vous pouvez personnaliser le fichier CommonResources.dll pour inclure l’ajout d’une page de garde personnalisée. Après avoir personnalisé le fichier, vous pouvez remplacer manuellement le fichier d’origine par le fichier personnalisé sur tous les postes de travail ou vous pouvez choisir une méthode automatisée pour remplacer le fichier.

Dans un environnement étendu, il est difficile et fastidieux de remplacer manuellement le fichier `CommonResources.dll file` par défaut par un fichier `CommonResources.dll` personnalisé. Vous pouvez utiliser un outil d’extraction automatique et de création de package (par exemple, WinZip Self-Extractor) pour traiter le fichier CommonResources.dll personnalisé avec le programme d’installation d’AEM Document Security Extension for Microsoft Office Ultérieurement, vous pouvez distribuer l’installation personnalisée à tous les postes de travail. Cette méthode réduit le temps nécessaire pour remplacer le fichier par défaut `CommonResources.dll` par un fichier personnalisé. Elle assure aussi que tous les postes de travail ont le fichier CommonResources.dll requis. L’outil d’extraction automatique et de création de package n’est qu’une des nombreuses méthodes possibles de remplacement automatique d’un fichier. Vous pouvez choisir n’importe quelle méthode qui convient à votre environnement.

Vous pouvez exécuter les étapes suivantes pour créer un package personnalisé du fichier `CommonResources.dll`avec le programme d’installation d’AEM Document Security Extension for Microsoft Office :

1. Installez un outil d’extraction automatique et de création de package. Par exemple, WinZip Self-Extractor.
1. Créez un nouveau dossier. Par exemple, NOM_DE_DOSSIER
1. Placez le programme d’installation initiale d’AEM Document Security Extension et le fichier CommonResources.dll dans le dossier que vous venez de créer.
1. Créez un fichier de commandes dans le dossier. Par exemple, NOM_DE_DOSSIER\Installer.bat
1. Ouvrez le fichier de commandes afin de le modifier et insérez le code suivant :

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   Si vous utilisez une autre version de LiveCycle ou d’AEM Forms on JEE indépendamment de LiveCycle Rights Management ES4 et version 11.0.0, remplacez le chemin d’accès de la clé de registre comme suit :

   * (Livecycle Rights Management ES2 et version 9.0) : *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 et version 10.0)
   * (Livecycle Rights Management ES4 et version 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms on JEE et versions ultérieures) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. Dans le code ci-dessus, remplacez toutes les instances de YOUR_FOLDER_NAME par le nom du dossier que vous avez créé à l’étape 2.
1. **(Pour le programme d’installation d’AEM Document Security extension for Microsoft Office avec une extension .exe uniquement)** Remplacez la ligne de code suivante :

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
avec

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Enregistrez et fermez le fichier batch.
1. Utilisez un outil d’extraction automatique et de création de package pour créer un package du dossier contenant le fichier CommonResources.dll personnalisé, le programme d’installation original d’AEM Document Security Extension et le fichier batch.

   >[!NOTE]
   >
   >Assurez-vous que le package à extraction automatique est configuré pour être exécuté en tant qu’administrateur et
   >exécute automatiquement le fichier batch une fois l’extraction terminée.

Désormais, le programme d’installation à extraction automatique d’AEM Document Security Extension pour Microsoft Office intègre le fichier CommonResources.dll et est prêt pour distribution.

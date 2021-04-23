---
title: Dépannage d’AEM Document Security Extension for Microsoft Office
description: Si vous rencontrez des problèmes lors de l’installation, de la configuration ou de l’utilisation d’AEM Document Security Extension for Microsoft Office, suivez les instructions figurant dans ce document.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
translation-type: ht
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---

# Dépannage d’AEM Document Security Extension for Microsoft Office {#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Dépannage des problèmes d’installation et de configuration {#troubleshootinginstallationandconfiguration}

Si vous rencontrez des problèmes pour installer et configurer AEM Document Security Extension for Microsoft Office, assurez-vous que vous avez soigneusement suivi les instructions figurant dans la section - Avant l’installation - de l’article [Installation](installing-configuring-aemdsext.md).

Si vous avez effectué l’installation et la configuration conformément aux instructions présentées dans la documentation et pour plus de détails sur des problèmes semblables à ceux que vous rencontrez, consultez les sections suivantes.

### Document Security Extension ne se charge pas lors du chargement des applications Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La propriété LoadBehavior dans le registre Windows spécifie le comportement d’exécution du module externe Document Security. Si la propriété LoadBehavior est définie sur 3, tous les modules externes sont chargés automatiquement. Avant d’installer Document Security Extension for Microsoft Office, assurez-vous que la valeur de la propriété LoadBehavior est définie sur 3.

1. Effectuez une sauvegarde du registre Windows avant d’apporter des modifications. Pour obtenir des instructions détaillées, consultez [Comment modifier le registre Windows](https://support.microsoft.com/fr-fr/kb/136393).
1. Dans l’éditeur de registre, accédez à HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin ou HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Définissez la valeur de la propriété **LoadBehavior** sur 3.

1. Fermez l’éditeur du registre.

Pour plus d’informations sur LoadBehavior, consultez l’article [Entrées du registre pour les modules complémentaires VSTO](https://msdn.microsoft.com/fr-fr/library/bb386106.aspx#LoadBehavior).

## Dépannage des tâches d’administration {#admintasks}

Cette section aborde les problèmes qui pourraient survenir avec votre installation d’AEM Document Security Extension.

### Les applications Microsoft Office ne se lancent pas correctement après l’installation de Document Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Pour garantir le démarrage correct des applications Office sur un ordinateur doté de Document Security Extension et de McAfee VirusScan avec activation de l’option d’analyse lors de l’accès (On-Access Scan), désactivez l’option de protection contre le débordement de la mémoire tampon (Buffer Overflow Protection) de la Console McAfee VirusScan.

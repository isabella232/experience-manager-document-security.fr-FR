---
title: Présentation d’AEM Document Security Extension for Microsoft® Office
description: À l’aide de Document Security Extension for Microsoft® Office, vous pouvez appliquer des paramètres prédéfinis de confidentialité à vos fichiers Microsoft® Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: f3456fa7243405a4986ac50540f8b578a6412a6c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 96%

---

# Présentation d’AEM Document Security Extension for Microsoft® Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office garantit que seules les personnes autorisées ont accès à vos fichiers Word, Excel et PowerPoint contenant votre propriété intellectuelle. À l’aide de Document Security Extension for Microsoft® Office, vous pouvez appliquer des paramètres prédéfinis de confidentialité à vos fichiers.

Document Security Extension for Microsoft® Office étend la protection des modules complémentaires LiveCycle Rights Management et Document Security pour Adobe Experience Manager Forms aux fichiers Word, Excel et PowerPoint et permet aux personnes utilisatrices autorisées disposant de ce logiciel de manipuler les fichiers protégés par une stratégie conformément aux paramètres de confidentialité établis dans la stratégie.

## Protection de la propriété intellectuelle à l’aide de Document Security {#how-document-security-protects-intellectual-property}

Document Security garantit que seules les personnes autorisées peuvent utiliser les fichiers contenant votre propriété intellectuelle. Grâce à Document Security, vous pouvez protéger les fichiers en appliquant des stratégies de confidentialité. A *policy* est un ensemble d’informations qui comprend des paramètres de confidentialité et une liste d’utilisateurs autorisés. Les paramètres spécifiés dans une stratégie déterminent dans quelle mesure un destinataire peut utiliser un fichier auquel vous appliquez cette stratégie. Vous pouvez par exemple indiquer si les destinataires peuvent imprimer ou copier du texte ou enregistrer des modifications.

Les administrateurs et les utilisateurs de Document Security créent des stratégies. Les administrateurs créent des stratégies organisationnelles accessibles à tous les utilisateurs autorisés. Les administrateurs ou coordinateurs de stratégies peuvent également créer des groupes de stratégies appelés *jeux de stratégies* mis à la disposition d’un sous-ensemble d’utilisateurs. Les utilisateurs peuvent créer leurs propres stratégies, qu’eux seuls peuvent utiliser. Les administrateurs, les coordinateurs de stratégies et les utilisateurs créent des stratégies à l’aide des pages web Document Security.

Bien qu’elles soient stockées dans Document Security, les stratégies sont appliquées aux fichiers via Word, Excel ou PowerPoint. Lorsque vous appliquez une stratégie à un fichier, les informations qu’il contient sont protégées par les paramètres de confidentialité spécifiés dans cette stratégie. Lorsque vous distribuez le fichier protégé par une stratégie, seules les personnes destinataires autorisées par cette stratégie peuvent accéder au contenu du fichier.

En utilisant une stratégie pour protéger un fichier, vous maintenez un contrôle continu sur ce document, même après sa distribution. Vous pouvez contrôler les événements afin de déterminer quand et comment les destinataires utilisent votre fichier, apporter des modifications à la stratégie, empêcher les utilisateurs de continuer à accéder au fichier et modifier la stratégie associée au fichier.

## Fonctionnement des stratégies {#how-policies-work}

Les stratégies contiennent des informations sur les utilisateurs autorisés et les paramètres de confidentialité à appliquer à la propriété intellectuelle. Parmi les utilisateurs, figurent tous les utilisateurs reconnus par Document Security du fait de l’inclusion dans une liste LDAP ou Active Directory liée. Il s’agit également de personnes qui ont été invitées à s’inscrire auprès de Document Security ou pour lesquelles l’administrateur a créé un compte.

Les paramètres de confidentialité d’une stratégie déterminent comment les destinataires peuvent utiliser les fichiers protégés par cette stratégie. Par exemple, les stratégies indiquent si les destinataires peuvent imprimer des fichiers, copier du contenu dans d’autres fichiers ou enregistrer des modifications dans des fichiers protégés. Les stratégies peuvent également spécifier différents paramètres de confidentialité pour divers utilisateurs.

Lorsque vous appliquez une stratégie à un fichier, les informations qu’il contient sont protégées par les paramètres de confidentialité spécifiés dans cette stratégie. Si vous distribuez le fichier, Document Security peut authentifier les destinataires qui tentent de l’ouvrir et autoriser l’accès en fonction des privilèges spécifiés dans la stratégie.

Après l’application d’une stratégie à un fichier, les paramètres de confidentialité de la stratégie peuvent être modifiés à tout moment. Cela vous permet d’ajouter ou de supprimer des personnes utilisatrices autorisées ou de modifier leurs privilèges une fois le fichier reçu. La stratégie appliquée au fichier peut être modifiée et l’accès au fichier peut être révoqué de sorte que toute personne disposant d’une copie du fichier ne puisse plus l’ouvrir.

Si l’utilisation hors connexion est autorisée par la stratégie, les destinataires peuvent également utiliser les fichiers protégés par la stratégie hors connexion (sans liaison avec Internet ou le réseau) pendant la période spécifiée dans la stratégie.

## Fonctionnement des fichiers protégés par une stratégie {#how-policy-protected-files-work}

Pour qu’une personne utilisatrice puisse ouvrir et manipuler les fichiers Word, Excel et PowerPoint protégés par une stratégie, cette stratégie doit la désigner comme destinataire ou lui accorder un accès anonyme, et la personne utilisatrice doit avoir installé Document Security Extension for Microsoft® Office. Pour communiquer un fichier protégé par une stratégie à une personne qui ne possède pas Document Security Extension for Microsoft® Office, procurez-lui une copie du logiciel ou expliquez-lui comment le télécharger sur votre site web. Si vous ne disposez pas du programme d’installation, vous pouvez le télécharger à partir de la [page des téléchargements](https://experienceleague.adobe.com/docs/experience-manager-document-security/using/download-installer.html?lang=fr).

Lorsqu’une personne utilisatrice tente d’ouvrir un fichier protégé par une stratégie, Document Security Extension for Microsoft® Office se connecte à Document Security pour l’authentifier. Si Document Security est configuré pour contrôler l’utilisation des fichiers, l’utilisateur voit une notification indiquant que l’utilisation des fichiers est contrôlée. Document Security détermine les autorisations de fichiers à accorder à l’utilisateur, qui peut ensuite utiliser le fichier en fonction des paramètres de stratégie, dans les conditions suivantes :

* indéfiniment ou pendant la période de validité spécifiée dans la stratégie ;
* jusqu’à ce que l’administrateur ou la personne ayant appliqué la stratégie révoque l’accès au fichier ou modifie la stratégie.

   Si la personne qui a appliqué la stratégie la modifie ou révoque l’accès au fichier, les autorisations de la personne utilisatrice concernant le fichier sont modifiées ou supprimées même si elle dispose déjà du fichier. Si le fichier lui-même a été révoqué, une URL peut être fournie à la personne utilisatrice pour obtenir une copie mise à jour.

   Les fichiers protégés par une stratégie peuvent être ouverts hors ligne (sans connexion Internet ni réseau), si la stratégie autorise l’accès hors ligne, pendant la durée de la période d’ouverture hors ligne spécifiée dans la stratégie. Lorsque la période d’ouverture hors connexion se termine, l’utilisateur doit se connecter et se synchroniser avec Document Security, ce qui démarre une nouvelle période d’ouverture.

   Si la stratégie permet d’enregistrer le fichier et qu’un utilisateur enregistre une copie du fichier protégé par une stratégie, celle-ci est automatiquement appliquée au fichier enregistré. Les événements tels que les tentatives d’ouverture du nouveau fichier sont également contrôlés et enregistrés comme pour le fichier original.

## Utiliser Document Security pour protéger vos fichiers {#using-document-security-to-protect-your-files}

Vous pouvez utiliser des stratégies pour protéger vos fichiers dans différentes situations.

Par exemple, une entreprise de fabrication accepte les offres de fournisseurs qui proposent des pièces pour un nouveau produit. L’entreprise de fabrication doit fournir aux entreprises candidates les informations exclusives pour finaliser leurs offres. Le fabricant utilise Document Security pour protéger les fichiers par le biais d’une stratégie qui permet aux candidats d’ouvrir les fichiers et d’afficher les informations. Cependant, les candidats ne peuvent pas modifier, imprimer ni copier les fichiers et les personnes dépourvues de l’autorisation nécessaire ne peuvent pas ouvrir les fichiers.

Après avoir accepté l’une des offres, le fabricant met à jour la stratégie afin de donner au candidat qui a réussi les autorisations d’imprimer, de copier et d’enregistrer les modifications localement, puis de supprimer les candidats qui n’ont pas réussi, de sorte qu’ils n’aient plus l’autorisation d’ouvrir les fichiers.

En travaillant avec l’entreprise candidate retenue, les ingénieurs et ingénieures de l’entreprise de fabrication modifient certaines des spécifications de conception contenues dans les dossiers. Pour publier les nouvelles spécifications, le fabricant révoque l’accès à certains fichiers et publie de nouvelles versions. Lorsque les ingénieurs de l’entreprise retenue tentent d’ouvrir le fichier, un message s’affiche indiquant que l’accès au fichier a été révoqué. Le message contient une URL permettant de télécharger une nouvelle version du fichier.

## Informations supplémentaires {#additional-information}

Les ressources de ce tableau peuvent vous aider à en savoir plus sur AEM Document Security :

<table >
 <tbody>
  <tr>
   <th><p>Pour plus d’informations sur</p> </th>
   <th><p>Voir</p> </th>
  </tr>
  <tr>
   <td><p>Aide à l’administrateur d’AEM forms</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/docs/experience-manager-65/forms/administrator-help/get-started/configure-general-aem-forms-settings.html?lang=fr">Aide à l’administrateur</a> ou, dans les pages administratives de Document Security, cliquez sur le lien Aide dans le coin supérieur droit d’une page.</p> </td>
  </tr>
  <tr>
   <td><p>Mises à jour des correctifs, notes techniques et informations supplémentaires sur cette version du produit</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home&amp;lang=fr#support">Support technique d’Experience Cloud</a></p> </td>
  </tr>
 </tbody>
</table>

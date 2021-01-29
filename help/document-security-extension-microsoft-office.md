---
title: Introduction à AEM Document Security Extension for Microsoft Office
description: A l’aide de Document Security Extension for Microsoft Office, vous pouvez appliquer des paramètres prédéfinis de confidentialité à vos fichiers Microsoft Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: tm+mt
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 23%

---


# Introduction à AEM Document Security Extension for Microsoft Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office garantit que seules les personnes autorisées ont accès à vos fichiers Word, Excel et PowerPoint contenant votre propriété intellectuelle. A l’aide de Document Security Extension for Microsoft Office, vous pouvez appliquer des paramètres prédéfinis de confidentialité à vos fichiers.

Document Security Extension for Microsoft Office étend la protection des modules complémentaires LiveCycle Rights Management et Document Security pour Adobe Experience Manager Forms aux fichiers Word, Excel et PowerPoint et permet aux utilisateurs, munis d’une autorisation et de ce logiciel, de manipuler les fichiers protégés par une stratégie conformément aux paramètres de confidentialité établis dans la stratégie.

## Protection de la propriété intellectuelle par la sécurité du Document {#how-document-security-protects-intellectual-property}

Document Security s&#39;assure que seules les personnes autorisées peuvent utiliser des fichiers contenant votre propriété intellectuelle. Grâce à Document Security, vous pouvez protéger les fichiers en appliquant des stratégies de confidentialité. Une *stratégie* est un groupe d’informations comprenant des paramètres de confidentialité et une liste d’utilisateurs autorisés. Les paramètres que vous spécifiez dans une stratégie déterminent comment un destinataire peut utiliser un fichier auquel vous appliquez la stratégie. Par exemple, vous pouvez indiquer si les destinataires peuvent imprimer ou copier du texte ou enregistrer des modifications.

Les administrateurs et utilisateurs de document Security créent des stratégies. Les administrateurs créent des stratégies d’entreprise accessibles à tous les utilisateurs autorisés. Les administrateurs ou les coordinateurs de jeux de stratégies peuvent également créer des groupes de stratégies appelés *jeux de stratégies* qui sont disponibles pour un sous-ensemble d&#39;utilisateurs. Les utilisateurs peuvent créer leurs propres stratégies, qu’ils peuvent uniquement utiliser. Les administrateurs, les coordinateurs de jeux de stratégies et les utilisateurs créent des stratégies à l’aide des pages Web Document Security.

Bien que les stratégies soient stockées dans Document Security, vous les appliquez aux fichiers via Word, Excel ou PowerPoint. Lorsque vous appliquez une stratégie à un fichier, les informations qu’il contient sont protégées par les paramètres de confidentialité spécifiés dans la stratégie. Lorsque vous distribuez le fichier protégé par une stratégie, seuls les destinataires autorisés par cette stratégie peuvent accéder au contenu du fichier.

L’utilisation d’une stratégie de protection d’un fichier vous permet de contrôler ce fichier en permanence, même après sa distribution. Vous pouvez contrôler les événements afin de déterminer quand et comment les destinataires utilisent votre fichier, d’apporter des modifications à la stratégie, d’empêcher les utilisateurs de continuer à accéder au fichier et de modifier la stratégie associée au fichier.

## Fonctionnement des stratégies  {#how-policies-work}

Les stratégies contiennent des informations sur les utilisateurs autorisés et les paramètres de confidentialité à appliquer à la propriété intellectuelle. Les utilisateurs peuvent être tout utilisateur reconnu par Document Security par l’inclusion dans une liste LDAP ou Principale Directory liée. Les utilisateurs peuvent également être des personnes qui ont été invitées à s’inscrire auprès de Document Security ou pour lesquelles l’administrateur a créé un compte.

Les paramètres de confidentialité d’une stratégie déterminent comment les destinataires peuvent utiliser les fichiers protégés par la stratégie. Par exemple, les stratégies indiquent si les destinataires peuvent imprimer des fichiers, copier du contenu dans d’autres fichiers ou enregistrer des modifications dans des fichiers protégés. Les stratégies peuvent également spécifier différents paramètres de confidentialité pour divers utilisateurs.

Lorsque vous appliquez une stratégie à un fichier, les informations qu’il contient sont protégées par les paramètres de confidentialité spécifiés dans la stratégie. Lorsque vous distribuez le fichier, Document Security authentifie les destinataires qui tentent d’ouvrir le fichier et autorise l’accès en fonction des privilèges spécifiés dans la stratégie.

Après l’application d’une stratégie à un fichier, les paramètres de confidentialité de la stratégie peuvent être modifiés à tout moment, ce qui vous permet d’ajouter ou de supprimer des utilisateurs autorisés ou de modifier les privilèges des utilisateurs une fois le fichier reçu. La stratégie appliquée au fichier peut être modifiée et l’accès au fichier peut être révoqué de sorte que toute personne disposant d’une copie du fichier ne puisse plus l’ouvrir.

Si la stratégie autorise l’accès hors connexion, les destinataires peuvent également utiliser hors connexion des fichiers protégés par une stratégie (sans connexion principale à Internet ou au réseau) pendant la période spécifiée dans la stratégie.

## Fonctionnement des fichiers protégés par une stratégie  {#how-policy-protected-files-work}

Pour qu’un utilisateur puisse ouvrir et manipuler les fichiers Word, Excel et PowerPoint protégés par une stratégie, cette stratégie doit le désigner comme destinataire ou lui autoriser un accès anonyme, et il doit avoir installé Document Security Extension for Microsoft Office. Pour communiquer un fichier protégé par une stratégie à une personne qui ne possède pas Document Security Extension for Microsoft Office, procurez-lui une copie du logiciel ou expliquez-lui comment le télécharger sur votre site Web. Si vous ne disposez pas du programme d’installation, vous pouvez le télécharger à partir de la [page de téléchargement](https://www.adobe.com/fr/products/livecycle/rightsmanagement/extension/downloads.html).

Lorsqu&#39;un utilisateur tente d&#39;ouvrir un fichier protégé par une stratégie, Document Security Extension for Microsoft Office se connecte à Document Security pour authentifier l&#39;utilisateur. Si Document Security est configuré pour contrôler l’utilisation des fichiers, l’utilisateur voit une notification indiquant que l’utilisation des fichiers est contrôlée. Document Security détermine les autorisations de fichiers à accorder à l’utilisateur et à ce dernier, puis il peut utiliser le fichier en fonction des paramètres de stratégie, dans les conditions suivantes :

* Pour la période de validité spécifiée dans la stratégie.
* Jusqu’à ce qu’un administrateur ou la personne ayant appliqué la stratégie révoque l’accès au fichier ou modifie la stratégie.

   Si la personne qui a appliqué la stratégie modifie la stratégie ou révoque l’accès au fichier, les autorisations de l’utilisateur pour le fichier sont modifiées ou supprimées même si l’utilisateur dispose déjà du fichier. Si le fichier lui-même a été révoqué, une URL peut être fournie à l’utilisateur pour obtenir une copie mise à jour.

   Les fichiers protégés par une stratégie peuvent être ouverts hors connexion (sans connexion Internet ou réseau), si la stratégie autorise l’accès hors connexion, pendant la durée de la période d’ouverture hors connexion spécifiée dans la stratégie. Lorsque la période d’ouverture hors connexion se termine, l’utilisateur doit se connecter et se synchroniser avec Document Security, qui début une nouvelle période d’ouverture.

   Si la stratégie permet d’enregistrer le fichier et qu’un utilisateur enregistre une copie du fichier protégé par une stratégie, celle-ci est automatiquement appliquée au fichier enregistré. Les événements, tels que les tentatives d’ouverture du nouveau fichier, sont également contrôlés et enregistrés de la même manière que pour le fichier d’origine.

## Utilisation de Document Security pour protéger vos fichiers {#using-document-security-to-protect-your-files}

Vous pouvez utiliser des stratégies pour protéger vos fichiers dans diverses situations.

Par exemple, un fabricant accepte les offres de fournisseurs qui fournissent des pièces pour un nouveau produit. Le fabricant doit fournir aux soumissionnaires les renseignements exclusifs dont ils ont besoin pour finaliser leurs soumissions. Le fabricant utilise Document Security pour protéger les fichiers avec une stratégie qui permet aux enchérisseurs d&#39;ouvrir les fichiers et de vue des informations. Cependant, les enchérisseurs ne peuvent pas modifier, imprimer ou copier les fichiers et toute personne qui n&#39;a pas l&#39;autorisation d&#39;ouvrir les fichiers est empêchée.

Après avoir accepté l&#39;une des offres, le fabricant met à jour la stratégie afin de donner à l&#39;enchérisseur qui a réussi les autorisations d&#39;imprimer, de copier et d&#39;enregistrer les modifications localement, et de supprimer les enchérisseurs qui n&#39;ont pas réussi, de sorte qu&#39;ils n&#39;aient plus l&#39;autorisation d&#39;ouvrir les fichiers.

En travaillant avec le soumissionnaire retenu, les ingénieurs du fabricant modifient certaines des spécifications de conception contenues dans les dossiers. Pour publier les nouvelles spécifications, le fabricant révoque l’accès à certains fichiers et publie de nouvelles versions. Lorsque les ingénieurs de l’enchérisseur qui a réussi à ouvrir le fichier tentent de le faire, un message s’affiche indiquant que l’accès au fichier a été révoqué. Le message contient une URL permettant de télécharger une nouvelle version du fichier.

## Informations supplémentaires {#additional-information}

Les ressources indiquées dans le tableau ci-dessous peuvent vous aider à mieux comprendre AEM Document Security :

<table >
 <tbody>
  <tr>
   <th><p>Pour plus d’informations sur</p> </th>
   <th><p>Voir</p> </th>
  </tr>
  <tr>
   <td><p>Aide sur AEM forms Administrator</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65_fr">Aide à l'administrateur</a> ou, dans les pages administratives de Document Security, cliquez sur le lien Aide dans le coin supérieur droit d'une page.</p> </td>
  </tr>
  <tr>
   <td><p>Mises à jour des correctifs, notes techniques et informations complémentaires sur cette version du produit</p> </td>
   <td><p><a href="https://helpx.adobe.com/fr/marketing-cloud/contact-support.html">Support technique de Marketing Cloud</a></p> </td>
  </tr>
 </tbody>
</table>


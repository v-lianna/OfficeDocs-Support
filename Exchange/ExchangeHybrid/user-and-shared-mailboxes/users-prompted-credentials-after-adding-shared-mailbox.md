---
title: Users prompted for credentials after adding a shared mailbox
description: Describes a scenario in which users are prompted for credentials in Outlook after they add a shared mailbox as a second Exchange email account in their existing Outlook profile.
author: Norman-sun
ms.author: v-swei
manager: dcscontentpm
audience: ITPro
ms.topic: troubleshooting
ms.prod: exchange-server-it-pro
localization_priority: Normal
ms.custom: 
- Exchange Hybrid
- CSSTroubleshoot
ms.reviewer: ernelso, jmartin
appliesto:
- Exchange Online
- Exchange Server 2016 Enterprise Edition
- Exchange Server 2016 Standard Edition
- Exchange Server 2013 Enterprise
- Exchange Server 2013 Standard Edition
- Exchange Server 2010 Enterprise
- Exchange Server 2010 Standard
search.appverid: MET150
---
# Users prompted for credentials after adding a shared mailbox as a second Exchange email account in their Outlook profile

_Original KB number:_ &nbsp; 3184064

## Problem

Consider the following scenario:

- You have a hybrid deployment of on-premises Microsoft Exchange Server and Microsoft Exchange Online in Office 365.
- You configured legacy on-premises public folders for a hybrid deployment.
- You create a shared mailbox that's located in Exchange Online.
- You assign Full Access permissions to one or more users.
- Users add shared mailboxes as second Exchange accounts in their existing Outlook profile.

In this scenario, users are repeatedly prompted for credentials when they open Outlook.

## Workaround

To work around the problem, move the shared mailbox to the on-premises environment.

## More information

Outlook tries to connect to the legacy public folders for the shared mailbox account. An error message that resembles the following is found in the RPC Client Access service log for this connection attempt:

> [LoginPermException] 'User SID: *SID*' can't act as owner of a MailUser
object '/o=ExchangeLabs/ou=Exchange Administrative Group (*Group*)/cn=Recipients/cn=189bd14f1ede49d7977
85e8f20d55edf-Shared Mail' with SID *SID* and MasterAccountSid S-1-5-10
 (StoreError=LoginPerm)

For more information, see [Configure legacy on-premises public folders for a hybrid deployment](/exchange/collaboration-exo/public-folders/set-up-legacy-hybrid-public-folders).

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/) or the [Exchange TechNet Forums](https://social.technet.microsoft.com/forums/exchange/home?category=exchange2010%2cexchangeserver).

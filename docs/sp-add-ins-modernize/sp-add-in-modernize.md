---
title: Modernizing your SharePoint add-in model implementations in Microsoft 365
description: 
ms.date: 09/25/2023
ms.prod: sharepoint
ms.localizationpriority: high
---

# Modernization guidance for existing SharePoint add-in model implementations in Microsoft 365

SharePoint add-in model was introduced as part of the SharePoint 2013 timeframe and it was also provided as an extensibility option for SharePoint Online (Microsoft 365). While SharePoint add-in model is currently still supported in the SharePoint Online, model and patterns and outdated and aren't recommended to be used.

Microsoft is looking into officially deprecating SharePoint add-in model by end of 2023 in SharePoint Online, with clear communications on the detailed end-of-life schedule for related features.

> [!IMPORTANT]
> Deprecation means official statement that the feature is no longer being invested, but it's still supported. End-of-life means that the feature will be discontinued and is no longer available for use.

> [!NOTE] 
> This upcoming deprecation announcement will impact SharePoint Online. There are no changes on the add-in model supportability within the SharePoint on-premises versions.

These upcoming changes are impacting SharePoint add-in model and also authentication patterns using the classic [SharePoint Online hosted Microsoft Azure Access Control Service](https://learn.microsoft.com/sharepoint/dev/sp-add-ins/authorization-code-oauth-flow-for-sharepoint-add-ins) (ACS) authentication patterns, used with the provided hosted add-ins and potentially with other unattended services connecting to SharePoint Online.

## Transformation technologies

Here's a high level table of the feature mapping as the add-in model implementation is transformed to use other long term supported features:

| Classic technology 	       | New technology
|--------------------	       |----------------
| SharePoint add-in          | SharePoint Framework
| Provider hosted add-in     | Azure AD registered apps
| App registration using ACS | Azure AD registered apps
| JSOM                       | Graph JS SDK & PnPjs library
| SharePoint Workflow        | Power Automate Flows

## Transformation guidance for the add-in techniques

Here's a list of all articles for the transformation guidance when moving away on using SharePoint add-in model, grouped based on the covered topic:

* Modern Authentication and Authorization
  * [Understanding Azure Active Directory and OAuth 2.0 in the context of SharePoint Online modern development](./Understanding-AAD-and-OAuth-for-SPO-modern.md)
  * [From Access Control Service applications to Azure Active Directory applications](./From-ACS-to-AAD-apps.md)
  * [Building Multi-tenant applications for SharePoint Online](./Multi-tenant-applications.md)
  * [Understanding Resource Specific Consent (RSC)](./Understanding-RSC-for-MSGraph-and-SharePoint-Online.md)
* Customizing the modern UI
  * [From App Parts and classic Web Parts to modern client-side SPFx Web Parts](./From-App-Parts-to-Modern-Web-Parts.md)
  * [From UI Extensions to SPFx List View Command Set](./From-UI-Extensions-to-ListView-Command-Sets.md)
  * [From status bars and notifications to SPFx Application Customizers](./From-Notifications-to-Application-Customizers.md)
  * [From classic dialogs to modern dialogs with SharePoint Framework](./From-classic-Dialogs-to-modern-Dialogs.md)
* Building modern SharePoint Online or Microsoft 365 solutions
  * [From SharePoint JavaScript Object Model to Client-side code and PnPjs](./From-JSOM-to-Client-Side.md)
  * [From Client Side Object Model (CSOM) to PnP Framework and PnP Core SDK](./From-CSOM-to-PnP-Libraries.md)
  * [From XSLT rendering to List Formatting](./From-XSLT-to-List-Formatting.md)
  * [From Remote Event Receivers to SharePoint Online Webhooks and Microsoft Graph Webhooks](./From-Remote-Event-Receivers-to-Webhooks.md)
  * [From SharePoint-hosted apps to client-side applications](./From-SharePoint-Hosted-to-Client-Side.md)
  * [From provider-hosted apps to AAD applications](./From-Provider-Hosted-to-AAD-applications.md)
  * [From SharePoint Add-in model Workflow Apps to Microsoft Power Automate](./From-Workflow-Apps-to-Power-Automate.md)
  * [Publishing modern SharePoint applications on Microsoft AppSource](./Publishing-modern-SharePoint-apps-on-AppSource.md)
* Modern Provisioning
  * [Modern provisioning of artifacts and Information Architecture](./Modern-Provisioning.md)

If some essential guidance isn't included, open an issue at the [SharePoint developer documentation](https://aka.ms/spdev-issues) and we'll help you as fast as possible with your specific question.

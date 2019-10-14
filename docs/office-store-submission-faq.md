---
title: AppSource submission FAQ
description: Answers to the most common questions about submitting an add-in to AppSource.
ms.date: 1/11/2018
localization_priority: Normal
---

# AppSource submission FAQ

For the most current version of the validation policies, see [Validation policies](validation-policies.md).

<a name="bk_q2"> </a>
## How can I avoid errors when submitting my add-in to AppSource?

To avoid common submission errors:

- Make sure that the version number on the submission form matches the version number in the add-in manifest.
    
    > [!NOTE]
    > Specify your add-in version using the following syntax: *a*  . *b*  . *c*  . *d*  Where *a*  is an integer between 1-9999, and each of *b*  , *c*  , *d*  are each integers between 0-9999. For example: 1.0.0.0 6.23.0.1.

- Make sure that all locations are SSL-secured (HTTPS).

- Make sure you that you specify an icon for your add-in in your package or manifest, and that the icon is correctly sized and formatted. For details, see [Icons](https://docs.microsoft.com/office/dev/add-ins/design/add-in-icons).

- Make sure your ID is unique.
 
  For example, do not create a manifest for a second add-in based on another add-in manifest you submitted without changing the ID in the new manifest.

- For Office Add-ins, make sure that you are using [manifest schema version 1.1](https://docs.microsoft.com/en-us/office/dev/add-ins/overview/add-in-manifests). For information about updating your manifest to version 1.1, see [Update to the latest JavaScript API for Office library and version 1.1 add-in manifest schema](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/update-your-javascript-api-for-office-and-manifest-schema-version). 

- For Office Add-ins, make sure that you specify a support URL in the **SupportUrl** element of your Office Add-in manifest. Your support URL should be a publicly available webpage, and should not require authentication. You cannot use personal social media pages or GitHub repositories for the support URL. You also can't use links to files hosted online such as a Word document on OneDrive, DropBox or Google Docs.

-  For all add-ins, make sure that your manifest is valid against the schema. For schema validation information, see [Schema reference for Office Add-ins manifests (v1.1)](https://docs.microsoft.com/en-us/office/dev/add-ins/overview/add-in-manifests) or [Schema reference for manifests of SharePoint Add-ins](https://msdn.microsoft.com/library/1f8c5d44-3b60-0bfe-9069-1df821220691(Office.15).aspx).

- Make sure your add-in is tested and is fully functional.

- Make sure your SharePoint Add-ins specify their supported locales. 
    
  If you don't specify supported locales, your add-in will not be accepted by AppSource. For details, see [Locale support information is required for all add-ins in AppSource](https://blogs.msdn.microsoft.com/officeapps/2012/10/12/locale-support-information-is-required-for-all-apps-in-the-sharepoint-store/).

- Make sure your OAuth client IDs match
    
  If your SharePoint Add-in accesses services using OAuth, make sure the OAuth client ID that you created in the Seller Dashboard matches the client ID in your add-in manifest.

- Your SharePoint Add-in package must conform to the Open Packaging Convention.

- Make sure that you submit a privacy link. 

- Make sure that any video links you submit actually go to a video file or a page that includes a video.

- If your Office Add-in is available on iOS, do not include "app" in the title or summary.

<a name="bk_q3"> </a>
## If I make updates to my submission, when do I have to resubmit it to AppSource?

If you make updates to the web service for your add-in, you do not have to resubmit it to AppSource. However, if you make changes to any items or data you submitted via the Seller Dashboard, such as the manifest, screenshots, icons, or submission form data, you need to resubmit it so that AppSource can implement those changes. You must resubmit add-ins with an updated manifest that includes a new version number. You must also make sure to update the version number in the submission form to match the version number of the new manifest.

<a name="bk_q3"> </a>
## What happens when I update my add-in to a new version in AppSource?

The following is the update process for Office Add-ins:

- You submit your revised add-in and add-in manifest to AppSource via [Partner Center](https://partner.microsoft.com/dashboard/office/overview). The revised add-in goes through the certification process, and when approved, is made available in AppSource. 

- You can choose to continue to offer the previous version of your add-in in AppSource, or you can unpublish the previous version via the Seller Dashboard. For details, see [Update, unpublish, and view metrics in the Seller Dashboard](update-unpublish-and-view-metrics.md).

- When an existing customer launches the updated add-in for the first time, a notification appears either in the task pane or the body of the document that prompts the user to update their add-in. When the user chooses **Update**, the latest version of the add-in launches.
    
  If the updated version includes new permissions, the user must consent to them.

> [!NOTE]
> You cannot have two or more versions of the same add-in in AppSource at the same time, because each add-in has a unique asset ID. If you create a new add-in to publish an updated version of your add-in without unpublishing the previous version, you will have two AppSource listings and will potentially split your customer base.

Updates to SharePoint Add-ins are handled by the license-management tools that are part of the SharePoint Add-in catalog. For more information, see [SharePoint Add-ins update process](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/sharepoint-add-ins-update-process).

<a name="bk_q4"> </a>
## Can I submit a paid add-in to AppSource?
All new add-ins submitted to AppSource via Partner Center are free. Existing paid add-ins migrated from Seller Dashboard will need to be moved to free by July 2020. For details, see [Moving from paid to free add-ins](moving-from-paid-to-free-addins.md). You can monetize your add-in through the Microsoft Commercial Marketplace; for details, see [Monetize your add-in](monetize-addins-through-microsoft-commercial-marketplace.md). 

## Can I submit an autohosted SharePoint Add-in to AppSource?

The Office 365 Autohosted Add-ins Preview program ended on June 30, 2014. You cannot create new autohosted add-ins in SharePoint. For more information, see [Update on Autohosted Add-ins Preview program](https://blogs.office.com/en-us/2014/05/16/update-on-autohosted-apps-preview-program/). For information about how to convert your autohosted add-in, see [Convert an autohosted SharePoint Add-in to a provider-hosted add-in](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/convert-an-autohosted-sharepoint-add-in-to-a-provider-hosted-add-in).
 
## How do I reference the JavaScript APIs for Office in my add-ins?

If your add-in uses the JavaScript APIs for Office, you must [reference the Microsoft-hosted Office.js file from its CDN URL](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/referencing-the-javascript-api-for-office-library-from-its-cdn). Don't include a copy of the Office.js file in your add-in, or reference a copy of the file hosted elsewhere.

<a name="bk_q7"> </a>
## Why do my apps and add-ins have to be SSL-secured?

Apps and add-ins that are not SSL-secured (HTTPS) generate unsecure content warnings and errors during use. For this reason, all apps and add-ins submitted to AppSource are required to be SSL-secured.
 
<a name="bk_q8"> </a>
## How do I declare language support?

Two aspects of your submission relate to supported languages: 

1. The languages you declare in your app package or manifest. You declare which languages your add-in supports differently depending on type:
    
   - For SharePoint Add-ins, declare language support by using the [SupportedLocales element (PropertiesDefinition complexType) (SharePoint Add-in Manifest)](https://docs.microsoft.com/en-us/sharepoint/dev/schema/supportedlocales-element-propertiesdefinition-complextypesharepoint-add-in-manif), in the add-in manifest within the add-in package. For more information, see [Explore the app manifest structure and the package of a SharePoint Add-in](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in).

   - For Office Add-ins that aren't dictionaries, declare language support by using the **DefaultLocale** and **Override** elements in your manifest. For more information, see [Localization for Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/localization).

   - For Office Add-ins that are dictionaries, you can also use the **TargetDialects** element within the add-in manifest. 

2. In Partner Center, you can select languages on the **Marketplace listings** page. 
    
    > [!NOTE]
    > You can declare more languages in your add-in package than are available for submission in Partner Center.

## See also

- [Submit your Office solution to AppSource via Partner Center](use-partner-center-to-submit-to-appsource.md)
- [Monetize your Office 365 add-in through Microsoft Commercial Marketplace](monetize-addins-through-microsoft-commercial-marketplace.md)

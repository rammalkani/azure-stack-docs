---
title: Prerequisites for installing Event Hubs on Azure Stack Hub
description: Learn about the required prerequisites, before installing the Event Hubs resource provider on Azure Stack Hub. 
author: BryanLa
ms.author: bryanla
ms.service: azure-stack
ms.topic: how-to
ms.date: 12/09/2019
ms.reviewer: jfggdl
ms.lastreviewed: 12/09/2019
---

# Prerequisites for installing Event Hubs on Azure Stack Hub

[!INCLUDE [preview-banner](../includes/event-hubs-preview.md)]

The following prerequisites must be completed before you can install Event Hubs on Azure Stack Hub. **Several days or weeks of lead time may be required** to complete all steps.

> [!IMPORTANT]
> These prerequisites assume that you've already deployed at least a 4-node Azure Stack Hub integrated system. The Event Hubs resource provider is not supported on the Azure Stack Development Kit (ASDK).

> [!IMPORTANT]
> Azure Stack Hub 2002 build version or higher is required by Event Hubs. Please note that Azure Stack Hub builds are incremental. For example, if you have [version 1908](/azure-stack/operator/release-notes?view=azs-1908#1908-build-reference) installed, you must first upgrade to [1910](/azure-stack/operator/release-notes?view=azs-1910#1910-build-reference), then to 2002. That is, you cannot skip builds in-between.

## Common prerequisites

[!INCLUDE [Common RP prerequisites](../includes/marketplace-resource-provider-prerequisites.md)]

## Event Hubs prerequisites

1. Procure public key infrastructure (PKI) SSL certificates for Event Hubs. The Subject Alternate Name (SAN) must adhere to the following naming pattern: `CN=*.eventhub.<region>.<fqdn>`. Subject Name may be specified, but it's not used by Event Hubs when handling certificates. Only the Subject Alternate Name is used. See [PKI certificate requirements](azure-stack-pki-certs.md) for the full list of detailed requirements.  

   ![example certificate](media/event-hubs-rp-prerequisites/certificate-example.png)

   > [!NOTE]
   > **PFX files must be password protected**. The password will be requested later during installation.

2. Be sure to review [Validate your certificate](azure-stack-validate-pki-certs.md). The article shows you how to prepare and validate the certificates you use for the Event Hubs resource provider. 

## Next steps

Next, [install the Event Hubs resource provider](event-hubs-rp-install.md).
---
title: Symantec to Microsoft Defender for Endpoint - Phase 1, Preparing
description: This is Phase 1, Prepare, of migrating from Symantec to Microsoft Defender for Endpoint.
keywords: migration, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: 
  - M365-security-compliance
  - m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
---

# Migrate from Symantec - Phase 1: Prepare for your migration

**Applies to:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Phase 1: Prepare](images/phase-diagrams/prepare.png)<br/>Phase 1: Prepare |[![Phase 2: Set up](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Phase 2: Set up](symantec-to-microsoft-defender-atp-setup.md) |[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Phase 3: Onboard](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*You are here!*| | |


**Welcome to the Prepare phase of [migrating from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. 

This migration phase includes the following steps:
1. [Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).
2. [Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).
3. [Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).

## Get Microsoft Defender for Endpoint

To get started, you must have Microsoft Defender for Endpoint, with licenses assigned and provisioned.

1. Buy or try Microsoft Defender for Endpoint today. [Visit Microsoft Defender for Endpoint to start a free trial or request a quote](https://aka.ms/mdatp). 
2. Verify that your licenses are properly provisioned. [Check your license state](production-deployment.md#check-license-state).
3. As a global administrator or security administrator, set up your dedicated cloud instance of Microsoft Defender for Endpoint. See [Microsoft Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).
4. If endpoints (such as devices) in your organization use a proxy to access the internet, see [Microsoft Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)). 

> [!NOTE]
> The Microsoft Defender Security Center is sometimes referred to as the Microsoft Defender for Endpoint portal. 

## Grant access to the Microsoft Defender Security Center

The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Microsoft Defender for Endpoint. To learn more, see [Overview of the Microsoft Defender Security Center](use.md).

Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC). We recommend using RBAC so that you have more granular control over permissions.

1. Plan the roles and permissions for your security administrators and security operators. See [Role-based access control](prepare-deployment.md#role-based-access-control).
2. Set up and configure RBAC. We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices. See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).<br/>
   If your organization requires a method other than Intune, choose one of the following options:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Advanced Group Policy Management](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)
3. Grant access to the Microsoft Defender Security Center. (Need help? See [Manage portal access using RBAC](rbac.md)).

## Configure device proxy and internet connectivity settings

To enable communication between your devices and Microsoft Defender for Endpoint, configure proxy and internet settings. The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:

|Capabilities  | Operating System | Resources |
|:----|:----|:---|
|[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 or later](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configure machine proxy and internet connectivity settings](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configure proxy and internet connectivity settings](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint on macOS: Network connections](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 or later](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configure and validate Microsoft Defender Antivirus network connections](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)  |[Microsoft Defender for Endpoint on Mac: Network connections](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, or higher LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender for Endpoint on Linux: Network connections](microsoft-defender-endpoint-linux.md#network-connections)  |

## Next step

**Congratulations**! You have completed the **Prepare** phase of [migrating from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!
- [Proceed to set up Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md).

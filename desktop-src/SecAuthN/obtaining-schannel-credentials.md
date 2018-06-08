---
Description: Credentials are required by the Schannel authentication process; both client and server must obtain valid credentials to establish a security context for message exchange. For an example that demonstrates this procedure, see Getting credentials.
ms.assetid: ee4a9908-7ba8-4701-84a4-c50b6b989e82
title: Obtaining Schannel Credentials
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Obtaining Schannel Credentials

Credentials are required by the Schannel authentication process; both client and server must obtain valid credentials to establish a [*security context*](https://msdn.microsoft.com/3e9d7672-2314-45c8-8178-5a0afcfd0c50) for message exchange. For an example that demonstrates this procedure, see [Getting credentials](getting-a-certificate-for-schannel.md).

Your application obtains credentials by calling the [**AcquireCredentialsHandle**](/windows/desktop/api/Sspi/) function, which returns a handle to the requested credentials. Because credentials handles are used to store configuration information, the same handle cannot be used for both client-side and server-side operations. This means that applications that support both client and server connections must obtain a minimum of two credentials handles.

In Windows XP, an [**SCHANNEL\_CRED**](/windows/desktop/api/Schannel/ns-schannel-_schannel_cred) structure specifies the following:

-   A security protocol
-   The allowable ciphers
-   Minimum and maximum cipher strengths
-   An [*X.509*](https://msdn.microsoft.com/28dba6ef-939f-4789-9789-ee6e0fef0177) certificate used for authentication — Required for server, optional for client unless server requests client authentication.

Pass the [**SCHANNEL\_CRED**](/windows/desktop/api/Schannel/ns-schannel-_schannel_cred) structure (via the *pAuthData* parameter) to the [**AcquireCredentialsHandle**](/windows/desktop/api/Sspi/) function. This function returns the credentials handle required to establish a [*security context*](https://msdn.microsoft.com/3e9d7672-2314-45c8-8178-5a0afcfd0c50).

For detailed information on setting the ciphers used with Schannel, see [Specifying Schannel Ciphers and Cipher Strengths](specifying-schannel-ciphers-and-cipher-strengths.md).

For information about certificates, see [Certificate and Certificate Store Functions](https://msdn.microsoft.com/9a65f73d-6f8c-4271-a2d0-d91ad952f9c6).

For an example that demonstrates opening a [*certificate store*](https://msdn.microsoft.com/db46def4-bfdc-4801-a57d-d568e94a2dbb) and locating a certificate to use for Schannel authentication, see [Getting a Certificate](getting-a-certificate-for-schannel.md).

 

 



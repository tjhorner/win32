---
Description: 'Initializes a PKCS \#10 certificate request object, wraps it in a CMC request object, submits the CMC request to an enterprise certification authority (CA), and saves the certificate returned by the CA in a file.'
ms.assetid: '0231da3b-a183-4443-8735-5affd24b145a'
title: enrollFromPublicKey
---

# enrollFromPublicKey

The enrollFromPublicKey sample initializes a PKCS \#10 certificate request object, wraps it in a CMC request object, submits the CMC request to an enterprise certification authority (CA), and saves the certificate returned by the CA in a file.

## Location

When you install the Microsoft Windows Software Development Kit (SDK), the sample is installed, by default, in the *%ProgramFiles%*\\Microsoft SDKs\\Windows\\v7.0\\Samples\\Security\\X509 Certificate Enrollment\\VC\\enrollFromPublicKey folder.

## Discussion

The enrollFromPublicKey sample:

1.  Processes the following command line arguments:
    -   The name of a certificate template.
    -   The name of a file in which to save the installed certificate as a base64-encoded byte array.
    -   An optional signing certificate template name. The template is used to create a signing certificate if none exists in the certificate store.
2.  Creates an [**IX509PrivateKey**](ix509privatekey.md) private key object and calls the [**Create**](ix509privatekey-create-method.md) method to create an asymmetric private key using the default cryptographic provider, key size, and [**KeySpec**](ix509privatekey-keyspec-property.md) values for the current computer.
3.  Retrieves the public key portion of the [**IX509PrivateKey**](ix509privatekey.md) object.
4.  Creates an [**IX509CertificateRequestPkcs10**](ix509certificaterequestpkcs10.md) object and initializes it by using the template specified on the command line and the public key.
5.  Creates an [**IX509CertificateRequestCmc**](ix509certificaterequestcmc.md) object and initializes it by using the PKCS \#10 request object.
6.  Retrieves an existing signing certificate or, if one cannot be found, creates a certificate request from the template specified on the command line and attempts to enroll it. The findCertByKeyUsage is defined in enrollCommon.cpp.
7.  Verifies the certificate chain.
8.  Creates an [**ISignerCertificate**](isignercertificate.md) object, initializes it by using the signing certificate, retrieves the [**ISignerCertificates**](isignercertificates.md) collection from the CMC request object, and adds the signing certificate object to the collection.
9.  Encodes the CMC request by using [*Distinguished Encoding Rules*](https://msdn.microsoft.com/library/windows/desktop/ms721573#-security-distinguished-encoding-rules-gly) (DER).
10. Creates an [**ICertConfig**](https://msdn.microsoft.com/library/windows/desktop/aa383268) object and uses it to retrieve a string that contains the CA configuration.
11. Creates a CryptoAPI [**ICertRequest2**](https://msdn.microsoft.com/library/windows/desktop/aa385041) object and uses it plus the strings that contain the CA configuration and the certificate request to submit the request to the CA.
12. Checks the status of the enrollment process and saves the installed certificate to a file. The EncodeToFileW function is defined in enrollCommon.cpp.

## Related topics

<dl> <dt>

[CMC Request](cmc-request.md)
</dt> <dt>

[PKCS \#10 Request](pkcs--10-request.md)
</dt> <dt>

[Using the Included Samples](using-the-included-samples.md)
</dt> </dl>

 

 



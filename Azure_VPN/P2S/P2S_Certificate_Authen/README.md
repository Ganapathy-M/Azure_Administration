# Create Self-sign root & client certificate Using Powershell

* If your organization using internal CA, you always can use it to generate relevant certificates for this exercise. If you do not have internal CA, we still can use self-sign certs to do the job.

* As first step I am going to create root certificate. In Windows 10 machine I can run this to create root cert first.

```
$cert = New-SelfSignedCertificate -Type Custom -KeySpec Signature `
-Subject "CN=ITECHKIROOT" -KeyExportPolicy Exportable `
-HashAlgorithm sha256 -KeyLength 2048 `
-CertStoreLocation "Cert:\CurrentUser\My" -KeyUsageProperty Sign -KeyUsage CertSign
```

* This will create root cert and install it under current user cert store.


* Then we need to create client certificate. We can do this using

```
New-SelfSignedCertificate -Type Custom -DnsName ITECHKICLIENT -KeySpec Signature `
-Subject "CN=ITECHKICLIENT" -KeyExportPolicy Exportable `
-HashAlgorithm sha256 -KeyLength 2048 `
-CertStoreLocation "Cert:\CurrentUser\My" `
-Signer $cert -TextExtension @("2.5.29.37={text}1.3.6.1.5.5.7.3.2")
```

* This will create cert called **ITECHKICLIENT** and install in same store location.

* Now we have certs in place. But we need to export these so we can upload it to Azure.

* To export root certificate,

    * Right click on root cert inside certificate mmc.
    * Click on Export
    * In private key page, select not to export private key
    * Select Base-64 encoded X.509 as export file format.
    * Complete the wizard and save the cert in pc.

* To export client certificate,

    * Use same method to export as root cert, but this time under private key page, select option to export private key.
    * In file format page, leave the default as following and click Next
    * Define password for the pfx file and complete the wizard.

**Note** – Only root cert will use in Azure VPN (Virtual Network Gateway), client certificate can install on other computers which need P2S connections.
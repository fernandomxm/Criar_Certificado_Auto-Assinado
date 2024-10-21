# Criar_Certificado_Auto-Assinado
Criar_Certificado_Auto-Assinado

**To convert a PFX file to a PEM file that contains both the certificate and private key:**
openssl pkcs12 -in filename.pfx -out cert.pem -nodes
**Pedirá a senha**

**Converter PEM para PFX**
openssl pkcs12 -export -out cert.pfx -inkey rootca.key -in cert.crt -in rootca.crt

**Extraindo CA**
openssl pkcs12 -in ${filename}.pfx -cacerts -chain -out ${filename}-ca.crt

**Convert cer to pem**
openssl x509 -in certificate.cer -out certificate.pem

**Conversion to separate PEM files**
**We can extract the private key form a PFX to a PEM file with this command:**
openssl pkcs12 -in filename.pfx -nocerts -out key.pem

**Exporting CRT the certificate only:**
openssl pkcs12 -in filename.pfx -clcerts -nokeys -out cert.crt

**Removing the password from the extracted private key:**
openssl rsa -in key.pem -out server.key

**Converter CRT para PEM**
cat server.crt server.key > server.pem

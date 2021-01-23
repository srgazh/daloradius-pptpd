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
		ipaddr = $IP   <- адрес сервера PPTPD
		secret = $PASS <- секретная фраза
}

2) PPTPD

/etc/pptpd.conf конфигурация PPTPD
/etc/ppp/pptpd-options опции PPTPD




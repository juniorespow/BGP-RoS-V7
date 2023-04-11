# BGP-RoS-V7
Script para se comunicar via API em um roteador com a versão 7 do RouterOS e coletar dados do BGP para monitoramento

Algumas caracteristicas do BGP na versão 7 do RouterOS precisam ser  levadas em consideração nesse script:

Segundo documentação no help.mikrotik.com na parte de Routing Protocol Overview a parte de BGP ROLES não esta totalmente implementada,
logo isso traz um problema para o monitoramento, pois a única chave que temos para saber que uma sessão eBGP ou iBGP esta UP é a informação
"established" - Logo quando não tem o código passa a informação '0' caso essa chave não exista.

Com o passar do tempo serão aplicadas melhorias e mais capturas de dados parao JSON.

Criei esse Script para funcionar em Zabbix, testado apenas no Zabbix 6.0.12 pora hora.

Sera Necessário criao Template no Zabbix para funcionar, posteriormente irei subir o template já testado.


Sobre os dados, são retornados em JSON, segue exemplo abaixo:

[{"NAME": "OPERADORA-01-V4-1", "IP": "50.50.1.9", "AS": 50, "MESSAGES": 1141, "UPTIME": 68130, "STATUS": 1}, {"NAME": "IX-SP-V4-1", "IP": "180.168.16.252", "AS": 5530, "MESSAGES": 1137, "UPTIME": 68130, "STATUS": 1}, {"NAME": "OPERADORA-01-V6-1", "IP": "4001:3ab3::1", "AS": 50, "MESSAGES": 1142, "UPTIME": 68130, "STATUS": 1}, {"NAME": "OPERADORA-03-V4-1", "IP": "192.190.0.1", "AS": 92, "MESSAGES": 937, "UPTIME": 56030, "STATUS": 1}, {"NAME": "OPERADORA-03-V6-1", "IP": "7002:4ac3::1", "AS": 92, "MESSAGES": 938, "UPTIME": 56030, "STATUS": 1}, {"IP": "bgp-IP6-4001:3ab3::1", "COUNT": 2929}, {"IP": "bgp-IP-180.168.16.252", "COUNT": 339}, {"IP": "bgp-IP-50.50.1.9", "COUNT": 4059}, {"IP": "bgp-IP-192.190.0.1", "COUNT": 4058}, {"IP": "bgp-IP6-7002:4ac3::1", "COUNT": 2929}]
# BGP-RoS-V7
Script para se comunicar via API em um roteador com a versão 7 do RouterOS e coletar dados do BGP para monitoramento

Algumas caracteristicas do BGP na versão 7 do RouterOS precisam ser  levadas em consideração nesse script:

Segundo documentação no help.mikrotik.com na parte de Routing Protocol Overview a parte de BGP ROLES não esta totalmente implementada,
logo isso traz um problema para o monitoramento, pois a única chave que temos para saber que uma sessão eBGP ou iBGP esta UP é a informação
"established" - Logo quando não tem o código passa a informação '0' caso essa chave não exista.

Com o passar do tempo serão aplicadas melhorias e mais capturas de dados parao JSON.

Criei esse Script para funcionar em Zabbix, testado apenas no Zabbix 6.0.12 pora hora.

Sera Necessário criao Template no Zabbix para funcionar, posteriormente irei subir o template já testado.
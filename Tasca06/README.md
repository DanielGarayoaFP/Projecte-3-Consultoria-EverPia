^^**Enunciat de la Tasca:** 

# **T06: Fonaments del servei DNS**

🧭 Guia d’Auditoria DNS — DigiCore / EverPia
📘 Fase Teòrica: Fonaments del Servei DNS
1.Jerarquia i Estructura del DNS

El DNS (Domain Name System) és una base de dades distribuïda en forma d’arbre que tradueix noms de domini en adreces IP.
L’estructura jeràrquica és:

Root (Arrel): Representada per un punt “.” al final del domini (per exemple, example.com.). Gestionada per 13 conjunts de Root Servers arreu del món.

TLD (Top Level Domain): Són dominis de primer nivell com .com, .org, .cat, .edu, etc.

Segon Nivell: El nom registrat per l’usuari o empresa, per exemple tecnocampus.cat.

Subdominis: Parts internes del domini principal, com www.tecnocampus.cat o mail.tecnocampus.cat.

2.Procés de Resolució de Noms

Quan un client vol accedir a un domini, es fa una consulta DNS:

Consulta Iterativa: El client pregunta a un servidor DNS, i aquest li indica quin altre servidor pot conèixer la resposta (no la resol completament).

Consulta Recursiva: El servidor DNS del client (normalment el de l’ISP) fa totes les consultes necessàries fins a obtenir la resposta final.

Servidors Autoritatius: Són aquells que tenen la informació original i verificable d’un domini.

Servidors Root: Punt de partida de totes les resolucions DNS.

3.Tipus de Zones

Zona Directa: Traducció de noms a IP (ex. tecnocampus.cat → 185.86.x.x).

Zona Inversa: Traducció d’IP a nom de domini (ex. 147.83.2.135 → host.upc.edu).

Zona Primària: Conté els fitxers originals de configuració DNS.

Zona Secundària: Una còpia de la zona primària utilitzada per redundància i equilibri de càrrega.

4.Tipus de Registres Clau (Records)

A: Associa un nom de domini a una adreça IPv4.

CNAME: Alias d’un altre nom de domini.

MX: Defineix els servidors de correu d’un domini.

NS: Indica els servidors de noms autoritatius per al domini.

TXT: Permet afegir informació addicional, com validacions SPF o dades de seguretat.

Conceptes Essencials

Resposta Autoritativa: Indica que la resposta prové d’un servidor amb autoritat sobre la zona. En eines com dig apareix com “aa” (authoritative answer).

TTL (Time To Live): Valor en segons que indica quant temps una resposta pot ser emmagatzemada en memòria cau abans de tornar-se a consultar.

SOA (Start of Authority): Conté informació clau sobre la zona: servidor principal, correu de l’administrador, número de sèrie, intervals de refresc i caducitat.

Reenviadors (Forwarders): Servidors DNS configurats per reenviar consultes a altres servidors.

Condicionals: S’apliquen només a dominis específics.

Incondicionals: Reenvien totes les consultes externes.

Resolució Local i mDNS: Els equips poden resoldre noms localment sense servidor DNS mitjançant el protocol mDNS (Multicast DNS), habitual en xarxes petites (per exemple, hostname.local).

🧪 Fase Pràctica: Diagnosi amb Eines CLI
🔍 1. Diagnosi Avançada amb dig (Linux/macOS)

Comanda 1: Consulta Bàsica de Registre A
Consulta: dig xtec.cat A
Anàlisi:

La resposta mostra la IP principal del domini (A record).

El camp TTL indica el temps de validesa de la resposta.

El camp SERVER mostra quin servidor DNS ha respost.

Comanda 2: Consulta de Servidors de Noms (NS)
Consulta: dig tecnocampus.cat NS
Anàlisi:

Retorna la llista de servidors autoritatius (nom i IP).

Permet identificar a quins servidors podem fer consultes directes.

Comanda 3: Consulta Detallada SOA
Consulta: dig escolapia.cat SOA
Anàlisi:

Mostra el servidor principal de la zona.

Inclou l’adreça de correu de l’administrador (format nom.admin@domini).

Mostra el número de sèrie, útil per sincronitzar zones primàries i secundàries.

Comanda 4: Consulta de Resolució Inversa
Consulta: dig -x 147.83.2.135
Anàlisi:

Retorna el nom associat a una IP.

Sovint indica el domini institucional o host específic corresponent a la IP.

💻 2. Comprovació amb nslookup (Windows / Linux / macOS)

Comanda 1: Consulta Bàsica no Autoritativa
Procediment:

Executar nslookup

Escriure set type=A

Consultar tecnocampus.cat
Anàlisi:

La resposta és “no autoritativa” perquè prové d’una memòria cau o d’un servidor intermediari, no directament del servidor autoritatiu.

Comanda 2: Consulta Autoritativa
Procediment:

Amb nslookup, escriure server IP (on IP és la d’un dels servidors NS del domini).

Consultar de nou tecnocampus.cat amb set type=A.
Anàlisi:

La resposta ara és “authoritative answer”.

S’observa informació directa del servidor que gestiona la zona.

Es pot veure un TTL diferent o detalls de registre més precisos.

🌐 3. Resolució Local i mDNS

En xarxes internes sense servidor DNS, els equips poden identificar-se mitjançant resolució local.

El protocol mDNS (Multicast DNS) permet resoldre noms de dispositius amb el sufix .local (exemple: impressora.local).

És habitual en entorns domèstics o d’oficina petita (sistemes macOS, Linux i Windows 10+).

No necessita servidor DNS extern, ja que les peticions es difonen per la LAN.

🧾 Resultats i Captures

A l’entrega final del projecte, s’han d’incloure:

Captures de pantalla de les cinc consultes (dig i nslookup).

Explicació sota cada captura amb l’anàlisi corresponent.

Fitxer guia.md amb aquest contingut teòric i pràctic.

Verificació del funcionament de resolució local (prova amb ping hostname.local).

📄 Conclusió

Aquest material forma part de la sessió formativa per al personal tècnic de DigiCore.
Permet entendre com funciona el DNS, com diagnosticar problemes habituals i com interpretar resultats de les principals eines CLI (dig, nslookup).
Un coneixement sòlid d’aquests conceptes és essencial per garantir una resolució de noms fiable, ràpida i segura dins de qualsevol infraestructura de xarxa.

[Resposta de la tasca](Tasca06)

[Video](Video)

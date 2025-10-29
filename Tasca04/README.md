
---

## **Plec de Condicions Tècniques (PCT)**

Projecte: Implementació del Servei de Directori LDAP per a Entorn de Proves Innovatech

Client (Beneficiari): Innovatech (Startup)  
Proveïdor (Consultora Tècnica): EverPia  
Data de Publicació: 17 d'octubre de 2025  
---

### **1\. Objecte de l'Encàrrec**

L'objecte del present Plec és la instal·lació, configuració i validació d'un servei **OpenLDAP** en un entorn virtualitzat basat en Ubuntu Server. Aquest servei s'ha de configurar per actuar com a directori centralitzat d'usuaris i grups per al domini de proves **innovatechXX.test**.

### **2\. Requeriments d'Infraestructura Inicial**

El consultor ha de verificar la correcta configuració de la infraestructura virtual abans d'iniciar la implementació:

| ID | Descripció del Requeriment | CONFIGURACIÓ INICIAL: Conectem el ssh a la terminal per tindre control remot.  
 |<img width="324" height="144" alt="1" src="https://github.com/user-attachments/assets/d2484627-3a50-4ac4-b68e-f26d7330ab8b" />

| :---- | :---- | :---- |
| **R.INF.01** | Configuració de la màquina Server (Server Hostname). | **server.innovatechXX.test La codificació i el canvi que hem realitzat 

!<img width="226" height="85" alt="2" src="https://github.com/user-attachments/assets/40fc1a00-0009-41b6-a12b-572be8592f96" /> |

| **R.INF.02** | Interfície de Xarxa Pública. | **NAT** (Per accés a Internet i descàrrega de paquets).

<img width="328" height="227" alt="3" src="https://github.com/user-attachments/assets/b383c86b-9281-4fd2-b469-b355640dae9a" /> |

| **R.INF.03** | Interfície de Xarxa Privada. | **Host-Only** (Per a comunicació privada amb el Client virtual  i la màquina física)

<img width="315" height="112" alt="4" src="https://github.com/user-attachments/assets/2a190ecd-32d9-4c2d-a78a-bda4d35c5c0b" />
|

### 

### **3\. Tasques d'Implementació i Configuració del Servidor LDAP**

La Consultora EverPia ha de complir estrictament amb les següents tasques d'instal·lació i configuració:

#### **3.1. Instal·lació i Configuració Base d'OpenLDAP**

| ID | Descripció de la Tasca | Detalls de la Configuració S'ha de mostrar el resultat de la comanda `slapcat` per validar la instal·lació base.  |
| :---- | :---- | :---- |
| **T.LDAP.01** | Instal·lació del servei OpenLDAP. | S'ha de mostrar el resultat de la comanda slapcat per validar la instal·lació base .**Un cop hem  afegit aquesta comanda afegim ham sudo IMPORTANT dpkg-reconfigure slap 

<img width="317" height="158" alt="5" src="https://github.com/user-attachments/assets/b45dafd3-2769-4f6e-a727-aabea8e6ebdd" />

| **T.LDAP.02** | Configuració de la base de dades. | **Nom del Domini:** innovatechXX.test**Ara afegim el nom de domini i acceptem a OK 

<img width="327" height="127" alt="6" src="https://github.com/user-attachments/assets/7ee74932-aea5-4f79-a858-f8307bd42cf9" />
|
| **T.LDAP.03** | Configuració de la contrasenya d'administrador. | **Contrasenya:** p@ssw0rd**Un com hem creat el domini DNS ens demanara una contrasenya en el nostre cas haurem de possar: p@ssw0rd I despres ens dira si volem que s’esborri la base de dades un cop es purgin el paquet slapd Li hem de donar a      YES  Activar aquesta funció per no interrompre ficher antics que te el sistema.**  |
| **T.LDAP.04** | Creació d'Unitats Organitzatives (OU) inicials. | S'han de crear dues OUs: **users** i **groups** mitjançant un fitxer **.ldif**. 

**<img width="331" height="278" alt="7" src="https://github.com/user-attachments/assets/89621568-052f-4541-aabb-5e147e8c1f0d" />

I en aquesta pantalla veiem que la funció va perfectament 

|<img width="333" height="153" alt="8" src="https://github.com/user-attachments/assets/4fa79909-9548-4c83-9ced-f309bace0c6c" />

| **T.LDAP.05** | Validació de les Unitats Organitzatives. | Realitzar una consulta amb **ldapsearch** que mostri totes les OUs creades al directori. **Esta guardat correctament   Un cop configurat el archiu comprovem que s’ha guardat correctament.**   |

#### **3.2. Gestió i Administració (LAM)**

| ID | Descripció de la Tasca | Detalls de la Configuració |
| :---- | :---- | :---- |
| **T.LAM.01** | Instal·lació del Gestor d'Usuaris LDAP (LAM). | S'ha de documentar la comanda d'instal·lació. |
| **T.LAM.02** | Accés Remot i Configuració. | Connectar a LAM des de la màquina física utilitzant l'adreça IP de la interfície **Host-Only**.**Instal·lació LDAP  Configuració directori usant LDAP   

<img width="330" height="195" alt="9" src="https://github.com/user-attachments/assets/23247b3c-e098-4ee0-b207-2f63c558ce5b" />

Fer un sudo su per ser administrador i apliquem el code: apt install ldap-account-manager \-y 

<img width="331" height="123" alt="10" src="https://github.com/user-attachments/assets/3388c985-1ea1-4a10-b7db-29cc85c5a87a" />

Ens conectem a la terminal fen un ssh usuari@192.168.56.101 i ja estem conectats a la terminal.  Ara hem de buscar per google a la nostra maquina el seguent: [http://192.168.56.101](http://192.168.56.101)**  |
| **T.LAM.03** | Configuració per defecte. | Establir la configuració predeterminada perquè els nous usuaris s'ubiquin a l'OU **users** i els nous grups a l'OU **groups**. **Ara entrem a la configuració LAN Ara li donem en aquesta nova pestaña a (Edita els perfils del servidor)

] ara afegim la contrasenya que es “ lam “ I ens donara el permis de entrar al servell del usuari.


  Ara a la segona pestanya **“Tipos de cuentas”** **configurarem** els **OUs** per usuaris i grups.  ![][image16   |
| **T.LAM.04** | Creació de Grups. | Crear dos grups de seguretat al directori: **tech** i **manager**.Hem de fer clic a guardar i ens portarà a l’apartat de admin en el cual hem de iniciar sesio ham el seguent usuari i la seguent contrasenya →**adminp@ssw0rd**  La primera vegada que entrem a OU hem de donar li a crear per tal de poder començar a crear els diferents group en els quals haurem d’afegir els usuaris determinats que ens dona la tasca → 
<img width="329" height="68" alt="11" src="https://github.com/user-attachments/assets/4d6c8dc8-3241-4f82-9b8c-67e52b7a167e" />

Ara haurem de crear dos grups de seguretat al directori: tech i manager. **Hem d’afegir el nom del Grup \< Donar-li ha Guardar \< Crear el altre Grup**

<img width="328" height="72" alt="12" src="https://github.com/user-attachments/assets/10faa43e-2f69-4dfb-bc0d-9dcb2b4f76cd" />  |

| **T.LAM.05** | Creació d'Usuaris de Prova. | Crear un usuari per a cada grup: **tech01** (membre de tech) i **manager01** (membre de manager).

<img width="330" height="119" alt="13" src="https://github.com/user-attachments/assets/c9e02f32-9ecb-4049-810d-34cf7f72f7a3" /> 
**tech01 i manager01, Els cuals hem de assignar a un grup d’aquesta manera→ tech01 → tech manager01 → manager **   **Un cop posat el nom de l'usuari hem de donarli a UNIX per poder modificar el grup el cual assignarem per cadascun →** 

*<img width="337" height="284" alt="14" src="https://github.com/user-attachments/assets/7b5aea96-44a6-44cd-954a-00c085c17394" />
Finalment **ja** haurem **administrat** i **configurat** el gestor d’usuaris LDAP LAM des de l’eina gràfica.  |

### 
### 


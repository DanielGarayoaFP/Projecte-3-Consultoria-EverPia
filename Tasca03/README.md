T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge)
Breu descripció
Un cop superada la fase de formació, ja esteu preparats per afrontar el repte dels nostres clients. Com ja es va explicar, tenim un nou i important client, el bufet d’advocats Garriga i associats un dels més prestigiosos de la ciutat, ha requerit els serveis de la nostra consultora. Gestiona una gran quantitat d'informació legal sensible, per la qual cosa la integritat, la disponibilitat (alta redundància) i la facilitat de gestió del seu emmagatzematge són d'importància crítica.
La direcció de "Garriga i Associats" ha expressat la necessitat urgent de renovar els seus sistemes de servidors per garantir que la informació estigui protegida contra fallades de disc i que l'espai pugui ser ampliat sense interrupcions.
Com a tècnics d'Everpia, teniu l'encàrrec de dissenyar i documentar les solucions d'emmagatzematge que compleixen aquests requisits tant en entorns Linux com Windows. Aquest disseny permetrà presentar al client una proposta de solució.
L'objectiu principal és dissenyar i documentar dues solucions d'emmagatzematge (una per servidors Linux i una per servidors Windows) que compleixin amb els principis d'alta disponibilitat, redundància i escalabilitat per al client. Com ha de ser una prova de concepte, no treballarem amb servidors, sinó que, per facilitat, usar màquines virtuals de sistemes operatius clients per documentar els procediments.
1. Part Linux: LVM amb Zorin OS
S'ha d'utilitzar la distribució Zorin OS (o una alternativa Linux compatible) per demostrar la utilitat del Logical Volume Manager (LVM).
Requisits de la Implementació i Demostració:
Configuració Inicial: Crear un grup de volums (VG) i un volum lògic (LV) utilitzant inicialment un mínim de dos discs durs (simulats) de 10 GB de capacitat. Aquest volum haurà estar formatat i muntat automàticament al sistema mitjançant l’edició de l’arxiu /etc/fstab.
Alta Disponibilidad: Implementar la configuració d’un mirall (lvm_mirror) que protegeix la informació davant la fallada d'un disc.
Instantànies (snapshots):  Crear i afegir dos discos de 10 GB al grup de volums. Crear un volum (lvm_dades) amb el primer disc afegit, formatar-lo i muntar-lo. A continuació afegir arxius al volum (poden ser imatges d’Internet). Usar el segon disc afegit per crear un snapshot (lv_snapshot) i documentar com es pot restaurar aquest snapshot, si per exemple, la informació del volum original es danyés.
Escalabilitat: Demostrar el procés d'ampliació. Usar l’espai que quedi lliure dins el grup de volums per ampliar el volum lv_dades.


2. Part Windows: Espais d'Emmagatzematge (Storage Spaces)
S'ha d'utilitzar Windows 11 (per demostrar les configuracions possibles mitjançant els Espais d'Emmagatzematge (Storage Spaces).
Requisits de la Implementació i Demostració:
Configuració inicial: Creació d'un Storage Pool: Crear un pool d'emmagatzematge inicialment amb tres discos de 10 GB (simulats).
Estudi de Configuracions: Demostrar i documentar la creació d'un Espai d'Emmagatzematge utilitzant:
Resiliència de Mirall (Mirroring): Usar dos dels discos. Comprovar que ofereix alta disponibilitat.
Mirall triple: desfer l’espai anterior i crear un amb els tres discos que sigui mirall triple. Justificar quins avantatges té respecte el mirroring.
Resiliència de Paritat (Parity): Explicant la seva eficiència d'espai en comparació amb el mirall. Afegir tant discos de 10 GB com siguin necessaris.
Demostració de la Gestió: Mostrar com es visualitza l'estat dels discos i del pool des de la consola de gestió de Windows, simulant la facilitat de manteniment.
Com treballareu i què lliurareu?
El treball serà en grup. En primer lloc, us dividireu en dos equips, un d’ells haurà de resoldre la gestió en els equips Linux mitjançant LVM, mentre que el segon ho farà en els equips Windows usant la tecnologia anàloga Espais d’Emmagatzematge. Un cop ja us heu dividit, individualment preparareu el guió de la tasca a realitzar, cercant les comandes, consultant el enllaços de documentació, etc. Posteriorment, cada parella realitzarà la seva part de la demostració. Finalment, la totalitat del grup revisa la documentació generada i cada membre la puja al seu repositori.
La documentació dels dos casos es farà en format Markdown, incloent imatges, explicacions, etc. dins una carpeta anomenada tasca03 dins del projecte. Com en casos anteriors, l’arxiu README.md de la carpeta, ha de contenir la descripció de la tasca i els enllaços per accedir als dos documents. 
La nota de la tasca és conjunta al grup, per tant, organitzeu-vos i tingueu una bona comunicació interna.
Penseu que posteriorment, haureu de presentar al client les conclusions de la vostra feina en una presentació conjunta.
Material de classe (disponible al Moodle)
LVM Linux
Espais d’emmagatzematge (Windows)



**Crear discos addicionals virtuals per al Storage Pool**

Obre la configuració de la VM.

A l’apartat Emmagatzematge (Storage), afegeix tres discos nous de 10 GB cadascun.

Desa i reinicia la VM.  
Que quedi així:  
![][image1]

**Hem de seleccionar els tres discos creats** 

**![][image2]**

**RESILIENCIA DE MIRALL**

Seleccionem dos discos a \< **Administrar espacios de almacenamiento de discos** \>

**![][image3]**

Un cop seleccionats aquests dos discos hem d'afegir el 

Tipos de resilencia**: Reflejo doble** 

**I en la mida màxima posem 20 GB** 

**Un cop assignats els dos discos eliminem un per comprovar que passaria si eliminem un.**

**![][image4]**

**Creem un arxiu per veure que succeeix si esborrem un disc:** 

**![][image5]**

**Un cop eliminat ens donarà una advertència de què ha desaparegut un disc**

**![][image6]**

**un cop eliminat un disc hem d'afegir un disc que agafi la mateixa referència que tenia el disc anterior.**

**![][image7]**

**Com podem veure seguim tenint els dos discos que teníem anteriorment i a més segueixen tenint la informació (en aquest cas arxiu) que tenia abans:**

**![][image8]**

**I ara podrem esborrar la unitat de disc perquè no surti més la seva exportació:**

**Mirall triple**  
Desfer l’espai anterior i crear un amb els tres discos que sigui mirall triple. Justificar quins avantatges té respecte al mirroring.  
    
**![][image9]**

**Després d'afegir 5 discos hem d'obrir la màquina virtual.**

**Seguidament hem d'obrir la gestió de discs i inicialitzar els discos:**

**![][image10]**

**![][image11]**

**Ara un cop afegit veurem la tolerancia a les fallades, hem eliminat 2 discos, amb la màquina virtual apagada, un cop hem eliminat aquests 2 discos hem d encedre la màquina i comprovar si la informació està encara.** 

**![][image12]**

**Com podem veure, no hi ha cap error, i un dels documents anteriorment creats apareixen  correctament.** 

**![][image13]**

**Com podem veure, ens surt advertència als discos que hem desactivat, un cop ens surt que estan desactivant hem d’activar-los un altre cop amb la màquina apagada**

**![][image14]**

**Un cop hem activat els discos novament, també 		ens surten tots els arxius correctament** 

**![][image15]**


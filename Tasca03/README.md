# T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge) 🧠💽

## Breu descripció

Un cop superada la fase de formació, ja esteu preparats per afrontar el repte dels nostres clients. El bufet d’advocats **Garriga i Associats**, un dels més prestigiosos de la ciutat, ha requerit els serveis de la nostra consultora.

Gestiona una gran quantitat d'informació legal sensible, per la qual cosa la **integritat**, la **disponibilitat** (alta redundància) i la **facilitat de gestió** del seu emmagatzematge són d'importància crítica.

La direcció ha expressat la necessitat urgent de **renovar els seus sistemes de servidors** per garantir que la informació estigui protegida contra fallades de disc i que l'espai pugui ser ampliat sense interrupcions.

---

## 🎯 Objectiu

Dissenyar i documentar **dues solucions d'emmagatzematge** (una per servidors Linux i una per servidors Windows) que compleixin amb els principis de:

- Alta disponibilitat
- Redundància
- Escalabilitat

> La demostració es farà amb màquines virtuals de sistemes operatius clients.

---

## 🐧 Part Linux: LVM amb Zorin OS

### Requisits de la Implementació i Demostració

- **Configuració Inicial**:  
  Crear un grup de volums (VG) i un volum lògic (LV) amb dos discos de 10 GB. Formatar-lo i muntar-lo automàticament via `/etc/fstab`.

- **Alta Disponibilitat**:  
  Implementar un **mirall LVM** (`lvm_mirror`) per protegir la informació davant la fallada d’un disc.

- **Instantànies (snapshots)**:  
  - Afegir dos discos de 10 GB al VG.
  - Crear un volum (`lvm_dades`) amb el primer disc, formatar-lo i muntar-lo.
  - Afegir arxius (ex. imatges d’Internet).
  - Crear un snapshot (`lv_snapshot`) amb el segon disc i documentar com restaurar-lo.

- **Escalabilitat**:  
  Ampliar el volum `lv_dades` amb l’espai lliure del grup de volums.

---

## 🪟 Part Windows: Espais d’Emmagatzematge (Storage Spaces)

### Requisits de la Implementació i Demostració

- **Configuració inicial**:  
  Crear un **Storage Pool** amb tres discos de 10 GB.

- **Estudi de Configuracions**:
  - **Mirroring**: Usar dos discos per alta disponibilitat.
  - **Parity**: Usar els tres discos i explicar l’eficiència d’espai.
  - **Mirall triple**: Afegir els discos necessaris.

- **Gestió**:  
  Mostrar l’estat dels discos i del pool des de la consola de gestió de Windows.

---

## 🧑‍🤝‍🧑 Com treballareu i què lliurareu?

- El treball és **en grup**.
- Dividiu-vos en dos equips:
  - Equip Linux (LVM)
  - Equip Windows (Storage Spaces)
- **Individualment**: prepareu el guió de la tasca, cerqueu comandes, consulteu documentació.
- **En parella**: realitzeu la demostració.
- **En grup**: reviseu la documentació i **pugeu-la al vostre repositori**.

### 📁 Documentació

- Format: **Markdown**
- Incloure: Imatges, explicacions, etc.
- Carpeta: `tasca03`
- Arxiu principal: `README.md` amb descripció i enllaços als dos documents.

> La nota és **conjunta**, així que organitzeu-vos bé i mantingueu una bona comunicació interna. 🗣️

---

## 🧑‍🏫 Presentació final

Haureu de presentar al client les **conclusions** de la vostra feina en una **presentació conjunta**.

---

## 📚 Material de classe (disponible al Moodle)

- [LVM Linux](https://docs.google.com/presentation/d/1EFSMfLQRM0wvxRFEvXLN0oaiBq3goWNQ/edit?usp=sharing&ouid=104728425662496836733&rtpof=true&sd=true)
- [Espais d’emmagatzematge (Windows)](https://docs.google.com/presentation/d/1Xi9atPzB6fmiLM0qmKP2PxBrixb-s-ZB/edit?slide=id.p1#slide=id.p1)
---
- [Documentacio Linux LVM](Documentacio.(Linux-LVM).md)
- [Windows](Windows.md)
- [Tornar a la pagina principal](../README.md)


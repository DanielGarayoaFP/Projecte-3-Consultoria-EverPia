# 📄 P04: Documentació servidor DNS

## 👋 Breu descripció

Benvinguts, consultors d’EverPia! 🚀

En aquesta tasca heu configurat un servidor DNS com a prova de concepte per al client **Digicore**. El servidor es troba actualment en una màquina virtual **Ubuntu Server**, i l’objectiu és documentar i publicar la configuració al vostre repositori de **GitHub** per facilitar la seva replicació en futurs entorns.

---

## 🛠️ Fase 1: Preparació de la connectivitat i extracció dels arxius

### 🔌 Pas 1.1: Configuració de la Interfície Host-Only
- Afegiu una segona interfície de xarxa a la màquina virtual.
- Configureu-la en mode **Host-Only**.
- Comproveu la connectivitat amb la màquina física.

### 📤 Pas 1.2: Còpia Segura dels Fitxers amb SCP
Utilitzeu el protocol **SCP** per transferir els fitxers de configuració:

- `/etc/bind/named.conf.options`
- `/etc/bind/named.conf.local`
- Fitxers de zones dins la carpeta: `/etc/bind/zones`

📌 Exemple de comanda SCP:
```bash
scp usuari@ip:/etc/bind/named.conf.options .
```
---
[Tornar a la pagina principal](..//README.md)


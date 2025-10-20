# Informe Tècnic: Implementació d’un Gestor de Contrasenyes

## 1. Introducció i Justificació

L’atac recent sofert per EverPia ha posat en evidència una de les vulnerabilitats més comunes en la seguretat digital: l’ús de contrasenyes febles o reutilitzades. Aquestes pràctiques obren la porta a atacs com:

- **Atacs de diccionari**: Els atacants proven paraules comunes i combinacions habituals fins a trobar una coincidència.
- **Credential stuffing**: Quan una contrasenya filtrada es reutilitza en altres serveis, els atacants poden accedir a múltiples comptes automàticament.
- **Brute force**: Amb eines automatitzades, es poden provar milers de combinacions fins a trobar la correcta.

Un **gestor de contrasenyes** permet:
- Generar contrasenyes úniques, llargues i segures per a cada servei.
- Emmagatzemar-les de forma segura, evitant haver de recordar-les totes.
- Emplenar automàticament formularis, millorant la productivitat i reduint errors.

## 2. Comparativa Tècnica

| Característica                  | **Bitwarden (Online)**                                | **KeePassXC (Offline)**                              |
|-------------------------------|--------------------------------------------------------|------------------------------------------------------|
| **Sincronització**             | Sí, entre dispositius mitjançant núvol                | No, només amb còpies manuals                        |
| **Xifratge**                   | End-to-end (AES-256) amb codi obert                    | Local, AES-256, arxiu KDBX                          |
| **Accés multidispositiu**      | Web, mòbil, escriptori, extensions navegador           | Només escriptori (portabilitat via USB)             |
| **Mode de funcionament**      | Núvol (amb opcions d'auto-hosting)                     | Totalment local                                     |
| **Codi obert**                 | Sí                                                     | Sí                                                   |
| **Facilitat d’ús**            | Alta, molt intuïtiu                                    | Mitjana, més tècnic                                 |
| **Model Freemium / Cost**      | Gratuït amb opcions premium                           | Gratuït completament                                |
| **Backup i restauració**       | Exportació JSON xifrada                                | Arxiu local .kdbx                                    |
| **Autocompletat**              | Sí (extensions navegador, mòbil)                       | Limitat (no en navegadors)                          |

## 3. Avantatges i Inconvenients

### 🔐 Bitwarden (Online)
**Avantatges:**
- Sincronització automàtica entre dispositius.
- Integració amb navegador per autocompletar.
- Còpia de seguretat automàtica si es fa servir el núvol.
- Accessible des de qualsevol lloc.

**Inconvenients:**
- Dependència del núvol (tot i que xifrat end-to-end).
- Potencial objectiu d’atacs si no es protegeix amb 2FA.

### 💾 KeePassXC (Offline)
**Avantatges:**
- No depèn de connexions externes (molt segur en entorns aïllats).
- Total control de la base de dades.
- Ideal per a usuaris avançats.

**Inconvenients:**
- Sincronització manual (copiar arxius, USB).
- No apte per usuaris poc tècnics.
- No autocompleta en navegadors de forma nativa.

## 4. Recomanació Final

Es recomana **Bitwarden** com a gestor de contrasenyes per al personal tècnic d’EverPia.

**Justificació:**
- El personal necessita accés ràpid i segur des de múltiples dispositius.
- Bitwarden ofereix una corba d’aprenentatge suau i una experiència intuïtiva.
- El xifratge end-to-end i el codi obert garanteixen seguretat i transparència.
- L’opció d’autenticació en dos factors (2FA) afegeix una capa extra de seguretat.

---
TORNAR A LA PAGINA PRINCIPAL; [GESTOR CONTRASENYES](README.md)
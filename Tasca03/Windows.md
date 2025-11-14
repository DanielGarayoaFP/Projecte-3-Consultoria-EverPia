
[Crear discos addicionals virtuals per al Storage Pool.md](https://github.com/user-attachments/files/23550687/Crear.discos.addicionals.virtuals.per.al.Storage.Pool.md)


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

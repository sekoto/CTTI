<style type="text/css">
img[alt="minipic"] { 
  max-width: 80px;
  float: left;
  padding-right: 15px;
}
img[alt="centrar"] { 
  margin: auto;
  max-width: 75%;
  display: block;
}
</style>


<img src="https://cburgales.github.io/CTTI/images/ET_map.png" alt="centrar" usemap="#planetmap">


<map name="planetmap">
  <area shape="rect" coords="10,50,240,90" alt="Sun" href="#0-principis-globals">
  <area shape="rect" coords="20,250,170,300" alt="Sun" href="#1-solucions-lldt">
  <area shape="rect" coords="175,250,325,300" alt="Sun" href="#2-arquitectura-lldt">
  <area shape="rect" coords="330,250,480,300" alt="Sun" href="#3-arquitectura-telco">
</map>

<map name="image-map">
    <area shape="rect" alt="solucions" title="solucions" href="solucions" coords="37,371,227,399">
    <area shape="rect" alt="solucions" title="solucions" href="solucions" coords="37,371,227,399">
    <area shape="rect" alt="lldt" title="lldt" href="arquitecturalldt" coords="242,369,457,400">
    <area shape="rect" alt="telco" title="telco" href="arquitecturatelco" coords="467,371,681,399">
</map>

### Índex dels principis de l'entorn de treball

- **[0. Principis globals](#0-globals)**

- **[1. Solucions LLdT](#1-solucions-lldt)**
  * [1.1 Disseny aplicacions escriptori](#11-disseny-aplicacions-escriptori)
  * [1.2 Tecnologia](#12-tecnologia )   
    + [1.2.1 Virtualització d'aplicacions](#121-virtualització-d'aplicacions)
  * [1.3 Cost i mateniment](#13-cost-i-mateniment)
&nbsp;
- **[2. Arquitectura LLdT](#2-arquitectura-lldt)**
  * [2.1. Dispositius](#21-dispositius)
  * [2.2 Terminals corporatius](#22-terminals-corporatius)
&nbsp;  
- **[3. Arquitectura TELCO](#3-arquitectura-telco)**
  * [3.1 Principis de disseny](#31-principis-de-disseny)
  * [3.2 Principis tecnologics](#32-principis-tecnologics)   
  * [3.3 Principis de cost i mateniment](#33-principis-de-cost-i-mateniment)

<!-- toc -->
&nbsp;
&nbsp;

# Introducció
&nbsp;
*Els principis d’arquitectura CTTI són les normes i directrius generals destinades a ser perdurables i rarament modificables i tenen com a objectiu informar i recolzar la forma en què CTTI vol que s’implementin les xarxes de telecomunicacions.*
&nbsp;
&nbsp;
&nbsp;
---

![minipic](/images/ET_icon.png)
# 0. Principis globals
&nbsp;
&nbsp;

* **0.1 Estandarització**. Cal vetllar perquè els dissenys d'alt nivell de les arquitectures de l'entorn de treball esdevinguin un model estàndar que permeti implemantar-lo a qualsevol escenari amb el mínim de canvis necessaris. 
  * [Estàndards de l'entorn de treball](https://gencat.sharepoint.com/:x:/s/arquitecturasicpd/EZseBopn5rlNunUw11ODpqkB4GjH8Xq1MpPlkc0lpERamg?e=uENvXu): Catàleg dels dissenys estàndards amb diferent abast: àmbit o transversal.

&nbsp;
&nbsp;
&nbsp;
&nbsp;

---
![minipic](/images/arq.png)
# 1. Solucions LLdT

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## 1.1 Disseny aplicacions escriptori

* **1.1.1 Usabilitat**. Tota aplicació implementada al lloc de treball ha d'estar orientada a l'usuari, tanmateix la facilitat d'ús de la solució juntament amb un bon rendiment de la mateixa donaran com a resultat una experiència d'usuari satisfactoria. Amb aquesta motivació caldrà realitzar les proves de qualitat i rendiment pertinents.

* **1.1.2 Desacoblada i multi-plataforma**. Les aplicacions Web són la tipologia d'aplicacions prioritaria per lliurar al lloc de treball pels múltiples beneficis que ofereixen: agnòstiques al SO, maximitzen la mobilitat de l'usuari, faciliten l'administració, etc. Si per motius funcionals, tecnològics o econòmics, es requreix implementar una aplicació escriptori al lloc de treball caldrà avaluar les tecnologies, APIs i Frameworks que millor encaixen per assolir aquests principis.

* **Interoperatbiltat**. 

## 1.2 Tecnologia

### 1.2.1 Virtualització d'aplicacions

La virtualització d'aplicacions és l'acte d'aïllar o desacoblar un recurs informàtic dels altres, mitjançant la generació d'un paquet que inclou tots els objectes i fitxers que requereixi l'aplicació per funcionar i amb l'objectiu de poder-la executar sense necessitat d'instal·lació. 

En aquells casos d'ús on la virtualització d'aplicacions esdevingui com el mètode d'implementació adient caldrà seguir els següents principis associats amb la creació, execució i manteniment del paquet. Els principals motius pels que s'utilitzarà aquesta tecnologia són:

1. Execució de múltiples versions o instàncies de la mateixa aplicació escriptori en el mateix entorn.
2. Remediar conflictes entre aplicacions.
3. Ritme d'actualitzacions de l'aplicació escriptori molt elevat.
4. Es requreixi un implementació o desimplementació de l'aplicació molt àgil.

Principis:

* **1.2.1.1 Filosofia de “micro-serveis” o “components desacoblats”** amb l’objectiu de maximitzar la reutilització dels mateixos alhora que es minimitzen els esforços i l’impacte al servei per mantenir el cicle de vida de les aplicacions. Entenem que es segueix aquesta filosofia quan s'assoleixen les següents premisses:
  * a)	Ús de dependències: es generarà un paquet independent per aquells components susceptibles de ser reutilitzats o que poden ser modificats i actualitzats sense afectar a la resta de components (p.e.: frameworks, runtimes, visors o editors de documents, plugins, etc).

  * b) 	Els paquets principals no han d’incloure paràmetres de configuracions específics de l'aplicació o del sistema (p.e.: strings de connexió, nom de BBDD, etc). Aquestes personalitzacions s'inclouran en un paquet diferent o s'implementaran mitjançant una eina de gestió de l'entorn d'usuari (UEM).

* **1.2.1.2 Simplicitat** del paquet i del perfil d'usuari. Els fitxers i claus de registre a mantenir seran els mínims necessaris perquè l'aplicació sigui completament funcional.

* **1.2.1.3 Auto-contingut i auto-configurat.** És necessari garantir que la combinació del paquet principal + paquets dependents incorporen el total de fitxers i claus de registre necessàries per treballar amb l'aplicació1. Tanmateix, cal evitar la necessitat de configuracions manuals mitjançant una parametrització pre-establerta. 

* **1.2.1.4 L’entorn d’execució (bombolla) ha de ser segur,** aplicant les mesures restrictives necessàries per permetre només la interoperabilitat amb el sistema i aquells serveis completament imprescindibles pel bon funcionament de l’aplicació.

* **1.2.1.5 Cal vetllar per la compatibilitat del paquet,** avaluant el correcte funcionament del mateix en les diverses versions de Windows suportades pel lloc de treball de la Generalitat de Catalunya, en aquelles arquitectures compatibles amb l'aplicació (32bit \ 64bit). Al [full de ruta de programari](https://qualitat.solucions.gencat.cat/estandards/estandard-full-ruta-programari/), s’informa quines són aquestes versions i compilacions de SO.

* **1.2.1.6 L’experiència d’usuari persistent**, sense importar des de quin terminal -gestionat- s’executi, per tant, l’aplicació ha d’estar preparada per l’ús de perfils roaming i serà al perfil de l’usuari on es redirigiran tots els fitxers de treball i aquells fitxers destinats a personalitzar la configuració de l’aplicació. 

* **1.2.1.7	El paquet ha d'estar preparat** per una completa desinstal·lació i una actualització automatitzada pels mecanismes establerts.

* **1.2.1.8	Cicle de vida inalterable**. La virtualització de l'aplicació no ha d'interferir en el cicle de vida de la mateixa, el qual haurà d'anar alineat amb la versió del SO i demés programari present en els terminals client on es pretén executar.


## 1.3 Cost i mateniment

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

---

![minipic](/images/lldt.png)
# 2. Arquitectura LLdT
&nbsp;
&nbsp;
&nbsp;
&nbsp;

## 2.1 Dispositius

## 2.2 Terminals corporatius

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

---
![minipic](/images/conn.png)

# 3. Arquitectura TELCO
&nbsp;
&nbsp;
&nbsp;
&nbsp;

## 3.1 Principis de disseny

* **3.1.1 Adaptabilitat**. Capacitat per acollir noves funcionalitats i/o tecnologies minimitzant els canvis estructurals i els costos d'implementació.

* **3.1.2 Escalabilitat**. Totes les solucions de xarxes de telecomunicacions han de suportar sense dificultats el creixement, moltes vegades continu, i sense que es tingui que redissenyar novament la solució. 

* **3.1.3 Disponibilitat**. S’ha d’establir el grau de disponibilitat per tota solució de xarxa de telecomunicacions. Aquest valor es mesurarà com el percentatge de temps de disponibilitat de la xarxa durant un temps indicat, o també es podrà valorar com el temps màxim permès que pugui estar caiguda la xarxa sense afectar als serveis principals de l’empresa. 

* **3.1.4 Rendiment**. Per tota solució de xarxes de telecomunicacions cal determinar les càrregues de treball màximes, per tal de poder-les absorbir. Els paràmetres fonamentals a tenir en compte pel correcte funcionament dels serveis dintre de la xarxa (Telefonia IP, Videoconferència, Correu Electrònic, Etc...) són l’amplada de banda (Bandwidth), la pèrdua de paquets (Packet loss), el retard (Latency) i la variació de retard (Jitter). 

* **3.1.5 Administració**. Tota xarxa de telecomunicacions haurà de permetre de forma senzilla la seva administració, monitorització, control d'esdeveniment i incidències, amb enfocament cap una gestió automatitzada. 

* **3.1.6 Automatització**. Tant la provisió com el manteniment de la xarxa de telecomunicacions haurà d’orientar-se cap a la màxima automatització dels seus processos.

* **3.1.7 Seguretat**. Tota xarxa de telecomunicacions haurà d’establir un nivell de seguretat mínim que permeti aplicar els següents punts:

  * **3.1.7.1 Traçabilitat**. Capacitat per identificar l’origen i les diferents etapes d’una connexió de xarxa.
  * **3.1.7.2 Control d’accés**. Capacitat per limitar l’accés a la xarxa.
  * **3.1.7.3 Auditoria**. Capacitat per enregistrar tots els accessos realitzats.

* **3.1.8 Simplicitat**. Tot disseny està orientat a la senzillesa, evitant sempre desenvolupar solucions complicades, que acabin sent posteriorment ingovernables. 

* **3.1.9 Provat**. Totes les noves solucions han de ser provades en un laboratori, per tal de revisar-les més enllà de la simulació i poder fer els ajustos necessaris. Obtenint així evidències de les proves efectuades, i conseqüentment del funcionament de la solució.


## 3.2 Principis tecnologics

* **3.2.1 Estabilitat**. Les solucions a aplicar en les xarxes de telecomunicacions haurien de ser solucions amb un cert recorregut, no es recomanable utilitzar solucions poc madures a nivell de producció. Encara que, en certes situacions s’avaluara implementar solucions emergents.

* **3.2.2 Evolució**. Monitoritzar la xarxa i els seus components per a identificar les necessitats de creixement o de canvi dels equipaments de xarxa, per tal de acollir les previsions e creixement, noves necessitats i/o la obsolescència tecnològica.

* **3.2.3 Minimitzar la dependència sobre els fabricants**. Cal evitar sempre que sigui possible les solucions propietàries, i maximitzar la compatibilitat amb la resta dels components i sistemes. Però, allunyant-nos de solucions massa heterogènies que puguin generar problemes de governança. 


##  3.3 Principis de cost i manteniment

* **3.3.1 Arquitectura mínima**. Cal tenir sempre en compte l’escalabilitat de la xarxa, i caldrà minimitzar al màxim el marge de creixement del disseny. Basat en el principi de la automatització s’aconsegueix una reducció dels costos i temps dels processos d’instal·lació i manteniment, i una arquitectura sostenible en el temps, que doni una bona rendibilitat. 
 
* **3.3.2 Benefici màxim al menor cost i risc possible**. La solució de xarxa de telecomunicacions no només haurà d’aconseguir recollir unes especificacions tècniques, també haurà de valorar la rendibilitat tant del disseny com de la seva implementació, evitant sempre duplicitats en els serveis de xarxa. D’aquesta manera, haurà de prendre un enfoc per tal d’abaratir els costos, mentre es garanteixen els requeriments de la solució.

* **3.3.3 Impacte d’actualització**. Cal pensar en l’impacte que pugui generar una actualització a nivell de software, o equipament hardware de la xarxa de telecomunicacions. Cal sempre valorar quins seran els possibles canvis dintre de la xarxa, quins riscos i millores aportarà.



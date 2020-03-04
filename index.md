<style type="text/css">
img[alt="minipic"] { 
  max-width: 80px;
  float: left;
  padding-right: 15px;
}
img[alt="centrar"] { 
  margin: 0 auto;
  text-align: center;
  max-width: 75%;
}
</style>


<img src="https://cburgales.github.io/CTTI/images/ET.png" alt="centrar">

<map name="planetmap">
  <area shape="rect" coords="23,300,185,330" alt="Sun" href="#ArquitecturaTELCO">
  <area shape="rect" coords="190,300,371,330" alt="Sun" href="#ArquitecturaTELCO">
  <area shape="rect" coords="375,300,575,330" alt="Sun" href="#arqtelco">
</map>

#### Índex dels principis de l'entorn de treball

- **[1. Solucions LLdT](#1-solucions-lldt)**
  * [1.1 Disseny aplicacions escriptori](#11-disseny-aplicacions-escriptori)
  * [1.2 Tecnologia](#12-tecnologia )   
    + [1.2.1 Virtualització aplicacions](#121-virtualització-aplicacions)
  * [1.3 Cost i mateniment](#13-cost-i-mateniment)
  

- **[2. Arquitectura LLdT](#2-arquitectura-lldt)**
  * [2.1. Global](#21-global)
  * [2.2 Terminals corporatius](#22-terminals-corporatius)
  
- **[3. Arquitectura TELCO](#3-arquitectura-telco)**
  * [3.1 Principis de disseny](#31-principis-de-disseny)
  * [3.2 Principis tecnologics](#32-principis-tecnologics)   
  * [3.3 Principis de cost i mateniment](#33-principis-de-cost-i-mateniment)

<!-- toc -->
&nbsp;
&nbsp;

# Principis d'arquitectura d'entorn de treball
&nbsp;
Els principis d’arquitectura CTTI són les normes i directrius generals destinades a ser perdurables i rarament modificables i tenen com a objectiu informar i recolzar la forma en què CTTI vol que s’implementin les xarxes de telecomunicacions.

&nbsp;
&nbsp;
&nbsp;

---
![minipic](/images/arq.png)
# 1. Solucions LLdT

&nbsp;
&nbsp;

## 1.1 Disseny aplicacions escriptori

## 1.2 Tecnologia

### 1.2.1 Virtualització aplicacions

## 1.3 Cost i mateniment

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

---

# 2. Arquitectura LLdT
![minipic](/images/lldt.png)
*Els principis d’arquitectura CTTI són les normes i directrius generals destinades a ser perdurables i rarament modificables i tenen com a objectiu informar i recolzar la forma en què CTTI vol que s’implementin les xarxes de telecomunicacions.*
  
---
## 2.1 Global

## 2.2 Terminals corporatius

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

---
# 3. Arquitectura TELCO
![minipic](/images/conn.png)
*Els principis d’arquitectura CTTI són les normes i directrius generals destinades a ser perdurables i rarament modificables i tenen com a objectiu informar i recolzar la forma en què CTTI vol que s’implementin les xarxes de telecomunicacions.*
  
---

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

<p>
<details>
 <summary>Index dels Principis</summary>

* **[Solucions LldT](#arqtelco)**
    * nested list 1
    * nested list 2
    
* **[Arquitectura LldT](#arqtelco)**

* **[Arquitectura Telco](#arqtelco)**
    * [Principis de disseny](#Principisdissenytelco)
    * [Principis tecnologics](#Principistecnotelco)
    * [Principis de cost i manteniment](#Principiscosttelco)
    
</details>
</p>


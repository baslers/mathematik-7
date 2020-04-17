% Brüche ordnen und vergleichen

---
revealjs-url: https://revealjs.com
theme: white
width: \"95%\"
height: \"95%\"
header-includes:
    <style>
    .beispiel {
      border:3px;
      border-style:solid;
      border-color:black;
      width:fit-content;
      margin:auto;
    }
    .wichtig {
      border:3px;
      border-style:solid;
      border-color:red;
      width:fit-content;
      margin:auto;
    }
    </style>
...

### 💡 Brüche erweitern und kürzen 💡
**Erweitern:** Zähler und Nenner werden mit der gleichen Zahl multipliziert.  
Beispiel:  
<img src=".\Abbildungen\Erweitern.png" style="float:center; max-width:25%">  

**Kürzen:** Zähler und Nenner werden mit der gleichen Zahl dividert.  
Beispiel:  
<img src=".\Abbildungen\Kürzen.png" style="float:center; max-width:25%">

### 💪🏼 Brüche erweitern und kürzen 💪🏼
1. <https://mathe.aufgabenfuchs.de/bruch/erweitern---kuerzen.shtml>

### 💡 Brüche gleichnamig machen 💡
Brüche gleichnamig machen heißt: Sie durch kürzen oder erweitern auf den selben Nenner zu bringen.  
Einen gemeinsamen Nenner findet man, indem man alle Nenner miteinander multipliziert.  
<div class="beispiel">
Beispiel:  
Gegeben Brüche: $\frac{1}{2}, \frac{2}{8}, \frac{3}{9}$  
Gemeinsamen Nenner finden: $2\cdot 8\cdot 9 = 144$  
Brüche erweitern:  
$144:2=72$, also $\frac{1\cdot 72}{2\cdot 72}$  
$144:8=18$, also $\frac{2\cdot 18}{8\cdot 18}=\frac{36}{144}$  
$144:9=16$, also $\frac{3\cdot 16}{9\cdot 16}=\frac{48}{144}$  
Gleichnamige Brüche: $\frac{72}{144}, \frac{36}{144}, \frac{48}{144}$  
</div>

### 💪🏼 Brüche gleichnamig machen 💪🏼
2. Finde einen gemeinsamen Nenner der gegebenen Brüche und mache die Brüche gleichnamig.  
Gegeben: <span id="gegebeneBrueche"></span>  
Gleichnamige Brüche:  
<table align="center" cellpadding="0" cellspacing="0">
  <tr>
    <td rowspan="2" id="ersterBruch" align="center" style="vertical-align : middle;text-align:center;"></td>
    <td style="border-bottom: 2px solid black;" align="center"><input type="text" id="ersterZaehler" style="font-size:1em;width:2em;text-align:center;"></td>
    <td rowspan="2" id="erstesErgebnis" align="center" style="vertical-align : middle;text-align:center;"></td>
  </tr>
  <tr>
    <td style="border-top: 2px solid black;" align="center" style="vertical-align : middle;text-align:center;"><input type="text" id="ersterNenner" style="font-size:1em;width:2em;text-align:center;"></td>
  </tr>
  <tr>
    <td rowspan="2" id="zweiterBruch" align="center" style="vertical-align : middle;text-align:center;"></td>
    <td style="border-bottom: 2px solid black;" align="center"><input type="text" id="zweiterZaehler" style="font-size:1em;width:2em;text-align:center;"></td>
    <td rowspan="2" id="zweitesErgebnis" align="center" style="vertical-align : middle;text-align:center;"></td>
  </tr>
  <tr>
    <td style="border-top: 2px solid black;" align="center"><input type="text" id="zweiterNenner" style="font-size:1em;width:2em;text-align:center;"></td>
  </tr>
  <tr>
    <td rowspan="2" id="dritterBruch" align="center" style="vertical-align : middle;text-align:center;"></td>
    <td style="border-bottom: 2px solid black;" align="center"><input type="text" id="dritterZaehler" style="font-size:1em;width:2em;text-align:center;"></td>
    <td rowspan="2" id="drittesErgebnis" align="center" style="vertical-align : middle;text-align:center;"></td>
  </tr>
  <tr>
    <td style="border-top: 2px solid black;" align="center"><input type="text" id="dritterNenner" style="font-size:1em;width:2em;text-align:center;"></td>
  </tr>
</table>  
<button type="button" id="auswertenButton" style="font-size: 1em;">Überprüfen</button><button type="button" id="resetButton" style="font-size: 1em;">Neue Brüche</button>
<script type="text/javascript">
  var ersterZaehler;
  var zweiterZaehler;
  var dritterZaehler;
  var ersterNenner;
  var zweiterNenner;
  var dritterNenner;
  const ersterZaehlerInput = document.getElementById("ersterZaehler");
  const zweiterZaehlerInput = document.getElementById("zweiterZaehler");
  const dritterZaehlerInput = document.getElementById("dritterZaehler");
  const ersterNennerInput = document.getElementById("ersterNenner");
  const zweiterNennerInput = document.getElementById("zweiterNenner");
  const dritterNennerInput = document.getElementById("dritterNenner");
  const erstesErgebnis = document.getElementById("erstesErgebnis");
  const zweitesErgebnis = document.getElementById("zweitesErgebnis");
  const drittesErgebnis = document.getElementById("drittesErgebnis");
  const gegebeneBrueche = document.getElementById("gegebeneBrueche");
  const auswertenButton = document.getElementById("auswertenButton");
  const resetButton = document.getElementById("resetButton");
  function reset(){
    ersterZaehler = Math.floor(Math.random()*10+1);
    zweiterZaehler = Math.floor(Math.random()*10+1);
    dritterZaehler = Math.floor(Math.random()*10+1);
    ersterNenner = Math.floor(Math.random()*10+1);
    zweiterNenner = Math.floor(Math.random()*10+1);
    dritterNenner = Math.floor(Math.random()*10+1);
    ersterZaehlerInput.value = "";
    zweiterZaehlerInput.value = "";
    dritterZaehlerInput.value = "";
    ersterNennerInput.value = "";
    zweiterNennerInput.value = "";
    dritterNennerInput.value = "";
    erstesErgebnis.innerHTML = "";
    zweitesErgebnis.innerHTML = "";
    drittesErgebnis.innerHTML = "";
    katex.render("\\frac{"+ersterZaehler+"}{"+ersterNenner+"},\\frac{"+zweiterZaehler+"}{"+zweiterNenner+"},\\frac{"+dritterZaehler+"}{"+dritterNenner+"}", gegebeneBrueche, {throwOnError: false});
    katex.render("\\frac{"+ersterZaehler+"}{"+ersterNenner+"}=",ersterBruch, {throwOnError:false});
    katex.render("\\frac{"+zweiterZaehler+"}{"+zweiterNenner+"}=",zweiterBruch, {throwOnError:false});
    katex.render("\\frac{"+dritterZaehler+"}{"+dritterNenner+"}=",dritterBruch, {throwOnError:false});
  }
  reset();
  function auswerten(){
    if(!(ersterNennerInput.value==zweiterNennerInput.value && zweiterNennerInput.value==dritterNennerInput.value)){
      erstesErgebnis.innerHTML = "Leider falsch, denn die Brüche sind nicht gleichnamig.";
      zweitesErgebnis.innerHTML = "";
      drittesErgebnis.innerHTML = "";
    }else{
      if(Math.round(100000*ersterZaehler/ersterNenner)==Math.round(100000*ersterZaehlerInput.value/ersterNennerInput.value)){
        erstesErgebnis.innerHTML = "Richtig!";
      }else{
        erstesErgebnis.innerHTML = "Leider falsch.";
      }
      if(Math.round(100000*zweiterZaehler/zweiterNenner)==Math.round(100000*zweiterZaehlerInput.value/zweiterNennerInput.value)){
        zweitesErgebnis.innerHTML = "Richtig!";
      }else{
        zweitesErgebnis.innerHTML = "Leider falsch.";
      }
      if(Math.round(100000*dritterZaehler/dritterNenner)==Math.round(100000*dritterZaehlerInput.value/dritterNennerInput.value)){
        drittesErgebnis.innerHTML = "Richtig!";
      }else{
        drittesErgebnis.innerHTML = "Leider falsch.";
      }
    }
  }
  auswertenButton.addEventListener("click", auswerten);
  resetButton.addEventListener("click", reset);
</script>

### 💡 Brüche gleichnamig machen 💡
Besserer Weg, um einen gemeinsamen Nenner zu finden:  
Brüche erst so weit wie möglich kürzen und dann das kleinste gemeinsame Vielfache der Nenner finden.  
<div class="beispiel">
Beispiel:  
Gegebene Brüche: $\frac{1}{2}, \frac{2}{8}, \frac{3}{9}$  
Kürzen: $\frac{2}{8}=\frac{1}{4}, \frac{3}{9}=\frac{1}{3}$  
kgV finden: kgV(2,4,3)=12  
Brüche erweitern:  
$12:2=6$, also $\frac{1\cdot 6}{2\cdot 6}=\frac{6}{12}$  
$12:4=3$, also $\frac{1\cdot 3}{4\cdot 3}=\frac{3}{12}$  
$12:3=4$, also $\frac{1\cdot 4}{3\cdot 4}=\frac{4}{12}$  
</div>


### 💡 Gemeine Brüche vergleichen 💡
Um zwei gemeine Brüche miteinander zu vergleichen, müssen sie gleichnamig gemacht werden.  
Der Bruch mit dem größeren Zähler ist auch der größere Bruch.  
<div class="beispiel">
Beispiel:  
$\frac{3}{5}>\frac{4}{7}$, denn  
$\frac{3}{5}=\frac{3\cdot 7}{5\cdot 7}=\frac{21}{35}$,  
$\frac{4}{7}=\frac{4\cdot 5}{7\cdot 5}=\frac{20}{35}$ und  
$21>20$
</div>

### 💪🏼 Gemeine Brüche vergleichen 💪🏼
3. Vergleiche die Brüche, indem du sie gleichnamig machst und <, > oder = auswählst.  
<span id="ersterBruchVergleich"></span>
<select id="vergleich" style="font-size: 1em;">
<option value="kleiner"><</option>
<option value="gleich">=</option>
<option value="groesser">></option>  
</select>
<span id="zweiterBruchVergleich"></span><span id="ergebnisVergleich"></span>  
<br>
<button type="button" id="auswertenVergleich" style="font-size: 1em;">Überprüfen</button><button type="button" id="resetVergleich" style="font-size: 1em;">Neue Brüche</button>
<script type="text/javascript">
  const ersterBruchVergleich = document.getElementById("ersterBruchVergleich");
  const zweiterBruchVergleich = document.getElementById("zweiterBruchVergleich");
  const vergleich = document.getElementById("vergleich");
  const auswertenButtonVergleich = document.getElementById("auswertenVergleich");
  const resetButtonVergleich = document.getElementById("resetVergleich");
  const antwort = document.getElementById("ergebnisVergleich");
  var ersterZaehler;
  var zweiterZaehler;
  var ersterNenner;
  var zweiterNenner;
  function resetVergleich(){
    ersterZaehler = Math.floor(Math.random()*11);
    zweiterZaehler = Math.floor(Math.random()*11);
    ersterNenner = Math.floor(Math.random()*10+1);
    zweiterNenner = Math.floor(Math.random()*10+1);
    vergleich.selectedIndex = -1;
    katex.render("\\frac{"+ersterZaehler+"}{"+ersterNenner+"}",ersterBruchVergleich,{throwOnError:false});
    katex.render("\\frac{"+zweiterZaehler+"}{"+zweiterNenner+"}", zweiterBruchVergleich, {throwOnError:false});
    antwort.innerHTML = "";
  }
  resetVergleich();
  function auswertenVergleich(){
    var auswahl = vergleich.selectedIndex;
    var ergebnis;
    if(Math.round(100000*ersterZaehler/ersterNenner)<Math.round(100000*zweiterZaehler/zweiterNenner)){
      ergebnis=0;
    }else if(Math.round(100000*ersterZaehler/ersterNenner)==Math.round(100000*zweiterZaehler/zweiterNenner)){
      ergebnis=1;
    }else if(Math.round(100000*ersterZaehler/ersterNenner)>Math.round(100000*zweiterZaehler/zweiterNenner)){
      ergebnis=2;
    }else{
      ergebnis=-2;
    }
    if(auswahl==ergebnis){
      antwort.innerHTML = "Richtig!";
    }else{
      antwort.innerHTML = "Leider falsch.";
    }
  }
  auswertenButtonVergleich.addEventListener("click", auswertenVergleich);
  resetButtonVergleich.addEventListener("click", resetVergleich);
</script>

### 💡 Gemeine Brüche in Dezimalbrüche umwandeln 💡
Dezimalbrüche können auf einen Blick miteinander verglichen werden.  
Um einen gemeinen Bruch in einen Dezimalbruch umzuwandeln, muss der Zähler durch den Nenner dividiert werden.

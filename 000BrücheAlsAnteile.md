% Brüche als Anteile

---
revealjs-url: https://revealjs.com
theme: white
width: \"95%\"
height: \"95%\"

...

###
<img src=".\Abbildungen\Torte.svg" style="float:center; max-width:50%">  

### 💡Brüche als Anteile💡
<img src=".\Abbildungen\BrücheAlsAnteile.png" style="float:center;max-width:30%">  
<ul>
<li>Der **Zähler** gibt die Anzahl der Teile an, die betrachtet werden.</li>
<li>Der **Nenner** gibt an, in wie viele Teile ein Ganzes zerlegt wird.</li>
</ul>
Beispiel: $\frac{2}{3}$ von 27kg sind
$\frac{2}{3}\cdot 27kg=2\cdot 27kg:3=18kg$

### 💪🏼Brüche als Anteile💪🏼
1. LB S. 7 Nr. 4
2. LB S. 7 Nr. 5

### 💡Brucharten💡
<img src=".\Abbildungen\Brucharten.png" style="float:center; max-width:50%">  
<font size="6">
<ul>
<li>Stammbruch: **Ein** Teil eines Ganzen; z.B. $\frac{1}{2}, \frac{1}{3}, \frac{1}{4}\dots$</li>
<li>Echter Bruch: Anteil, der **kleiner** als das Ganze ist, z.B. $\frac{1}{4}, \frac{2}{4}, \frac{3}{4}$</li>
<li>Unechter Bruch: Anteil, der **gleich** oder **größer** als das Ganze ist, z.B. $\frac{4}{4}, \frac{5}{4}, \frac{6}{4}, \dots$</li>
<li>Gemischter Bruch: Unechter Bruch, der in ganzzahligem Anteil und verbleibendem Anteil unterteilt wird, z.B. $1\frac{1}{3}, 2\frac{3}{4}, \dots$</li>
<li>Dezimalbruch: Bruch, der als Dezimalzahl mit Komma beschrieben wird, z.B. $0.5, 0.25, 0.\overline{3}\dots$</li>
</ul>
</font>

### 💪🏼Brucharten 💪🏼
3. LB S. 7 Nr. 6  

4. Um welche Art von Bruch handelt es sich?  

<div id="aufgabeBrucharten"></div>
<form>
  <fieldset>
    <ul>
      <li>
        <label>
          <input type="checkbox" name="bruch" id="stammbruch">
          Stammbruch
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="bruch" id="echterBruch">
          Echter Bruch
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="bruch" id="unechterBruch">
          Unechter Bruch
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="bruch" id="gemischterBruch">
          Gemischter Bruch
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="bruch" id="dezimalbruch">
          Dezimalbruch
        </label>
      </li>
    </ul>
  </fieldset>
  <button type="button" id="auswerten">Überprüfen</button>
  <p id="ergebnis"></p>
  <button type="button" id="reset">Neue Zahl</button>
</form>

<script>
  const aufgabeBrucharten = document.getElementById("aufgabeBrucharten");
  const auswertenButton = document.getElementById("auswerten");
  const resetButton = document.getElementById("reset");
  const ergebnis = document.getElementById("ergebnis");
  const stammbruch = document.getElementById("stammbruch");
  const echterBruch = document.getElementById("echterBruch");
  const unechterBruch = document.getElementById("unechterBruch");
  const gemischterBruch = document.getElementById("gemischterBruch");
  const dezimalbruch = document.getElementById("dezimalbruch");
  var rand;
  var nenner;// = Math.floor(Math.random()*100+2);
  var zaehler;// = Math.floor(Math.random()*100+1);
  var koef;
  function resetFunction(){
    ergebnis.innerHTML = "";
    stammbruch.checked = false;
    echterBruch.checked = false;
    unechterBruch.checked = false;
    gemischterBruch.checked = false;
    dezimalbruch.checked = false;
    rand = Math.floor(Math.random()*6);
    switch (rand) {
      case 0:
        nenner = Math.floor(Math.random()*100+2);
        katex.render("\\frac{1}{"+nenner+"}", aufgabeBrucharten, {throwOnError: false});
        break;
      case 1:
        do{
          zaehler = Math.floor(Math.random()*100+2);
          nenner = Math.floor(Math.random()*100+3);
        }while(zaehler>=nenner);
        katex.render("\\frac{"+zaehler+"}{"+nenner+"}", aufgabeBrucharten, {throwOnError: false});
        break;
      case 2:
        do{
          zaehler = Math.floor(Math.random()*100+2);
          nenner = Math.floor(Math.random()*100+1);
        }while(zaehler<nenner);
        katex.render("\\frac{"+zaehler+"}{"+nenner+"}", aufgabeBrucharten, {throwOnError: false});
        break;
      case 3:
        do{
          zaehler = Math.floor(Math.random()*100+1);
          nenner = Math.floor(Math.random()*100+2);
          koef = Math.floor(Math.random()*100+1);
        }while(zaehler>=nenner);
        katex.render(koef+"\\frac{"+zaehler+"}{"+nenner+"}", aufgabeBrucharten, {throwOnError: false});
        break;
      case 4:
        koef = Math.floor(Math.random()*50)*Math.floor(Math.random()*3);
        katex.render(""+koef+"."+Math.floor(Math.random()*100+1), aufgabeBrucharten, {throwOnError: false});
        break;
      case 5:
        koef = Math.floor(Math.random()*50)*Math.floor(Math.random()*3);
        katex.render(""+koef+".\\overline{"+Math.floor(Math.random()*100+1)+"}", aufgabeBrucharten, {throwOnError: false});
        break;
    }
  }
  resetFunction();
  auswertenButton.addEventListener("click", auswertenFunction);
  resetButton.addEventListener("click", resetFunction);
  function auswertenFunction(){
    if(rand==0){
      if(!unechterBruch.checked && !gemischterBruch.checked && !dezimalbruch.checked){
        if(stammbruch.checked && echterBruch.checked){
          ergebnis.innerHTML = "Richtig!";
        }else if(stammbruch.checked || echterBruch.checked){
          ergebnis.innerHTML = "Richtig, aber noch nicht vollständig.";
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }else{
        ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
      }
    }
    if(rand==1){
      if(!stammbruch.checked && !unechterBruch.checked && !gemischterBruch.checked && !dezimalbruch.checked){
        if(echterBruch.checked){
          ergebnis.innerHTML = "Richtig!";
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }else{
        ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
      }
    }
    if(rand==2){
      if(!stammbruch.checked && !echterBruch.checked && !gemischterBruch.checked && !dezimalbruch.checked){
        if(unechterBruch.checked){
          ergebnis.innerHTML = "Richtig!";
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }else{
        ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
      }
    }
    if(rand==3){
      if(!stammbruch.checked && !echterBruch.checked && !dezimalbruch.checked){
        if(unechterBruch.checked && gemischterBruch.checked){
          ergebnis.innerHTML = "Richtig!";
        }else if(unechterBruch.checked || gemischterBruch.checked){
          ergebnis.innerHTML = "Richtig, aber noch nicht vollständig.";
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }else{
        ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
      }
    }
    if(rand==4 || rand==5){
      if(koef == 0){
        if(!stammbruch.checked && !unechterBruch.checked && !gemischterBruch.checked){
          if(echterBruch.checked && dezimalbruch.checked){
            ergebnis.innerHTML = "Richtig!";
          }else if(echterBruch.checked || dezimalbruch.checked){
            ergebnis.innerHTML = "Richtig, aber noch nicht vollständig.";
          }else{
            ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
          }
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }else{
        if(!stammbruch.checked && !echterBruch.checked && !gemischterBruch.checked){
          if(unechterBruch.checked && dezimalbruch.checked){
            ergebnis.innerHTML = "Richtig!";
          }else if(unechterBruch.checked || dezimalbruch.checked){
            ergebnis.innerHTML = "Richtig, aber noch nicht vollständig.";
          }else{
            ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
          }
        }else{
          ergebnis.innerHTML = "Falsch, versuche es weiter oder sieh dir nochmal die Definitionen an.";
        }
      }
    }
  }
</script>

### 💪🏼Brucharten 💪🏼
5. <https://mathe.aufgabenfuchs.de/bruch/bruchteile.shtml>

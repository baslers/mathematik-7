% Test zu Brüchen

---
header-includes:
    <style>
      body{
        font-family:sans-serif;
        counter-reset:aufgabe;
      }
      .title{
        display:none;
      }
      .aufgabe::before{
        counter-increment:aufgabe;
        content:"Aufgabe " counter(aufgabe) ":" " ";
      }
    </style>

---

<table style="width:100%; table-layout:fixed; border-style:solid; border-color:black; font-family: sans-serif">
  <tr>
    <td style="text-align:left; height:1.5em">Mathematik</td>
    <td style="text-align:center; height:1.5em"><span style="font-weight:bold">Test</span></td>
    <td style="text-align:right; height:1.5em">Datum</td>
  </tr>
  <tr>
    <td style="text-align:left; height:1.5em">Klasse</td>
    <td style="text-align:center; height:1.5em">Brüche</td>
    <td style="text-align:right; height:1.5em">Punkte: ____/____</td>
  </tr>
  <tr>
    <td style="text-align:left; height:1.5em">Name:</td>
    <td style="text-align:center; height:1.5em"></td>
    <td style="text-align:right; height:1.5em">Note: ____</td>
  </tr>
</table>
<div style="font-weight:bold; text-align:center">Alle Lösungswege sind ordentlich, vollständig und nachvollziehbar aufzuschreiben.</div>
<div style="font-weight:bold; text-align:center">Erlaubte Hilfsmittel: Taschenrechner, Tafelwerk, Schreib- und Zeichenutensilien</div>  
<br><br>
<div style="float:left"><span class="aufgabe" style="font-weight:bold">Gib jeweils den grau gefärbten Anteil als Bruch an.</span></div>
<div style="float:right">(___/3)</div>
<div style="clear:both"></div>
a) <img id="Kreis_Grafik" style="max-width:20%">
<script type="text/javascript">
  var z = Math.floor(Math.random()*9);
  var n = Math.floor(Math.random()*9);
  while(z>n || z==0){
    z = Math.floor(Math.random()*9);
    n = Math.floor(Math.random()*9);
  }
  document.getElementById("Kreis_Grafik").src = ".\\\Abbildungen\\\Kreis_"+z+"_"+n+".png";
</script>

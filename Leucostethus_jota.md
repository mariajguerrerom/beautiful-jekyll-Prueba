---
layout: page
title: "Leucostethus jota"
output: html_document
---


<style>
/* CSS para las pestañas */
.tab {
  overflow: hidden;
  border: 1px solid #ccc;
  background-color: #f1f1f1;
}
.tab button {
  background-color: inherit;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 14px 16px;
  transition: 0.3s;
}
.tab button:hover {
  background-color: #ddd;
}
.tab button.active {
  background-color: #ccc;
}
.tabcontent {
  display: none;
  padding: 6px 12px;
  border: 1px solid #ccc;
  border-top: none;
}
/* CSS para audios */
.audio-container {
  display: flex;
  flex-direction: column;
}
.audio-container audio {
  margin-bottom: 10px;
}
/* Ocultar el título en la página */
body h1 {
  display: none;
}
</style>


<script>
function openTab(evt, tabName) {
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("tabcontent");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].style.display = "none";
  }
  tablinks = document.getElementsByClassName("tablinks");
  for (i = 0; i < tablinks.length; i++) {
    tablinks[i].className = tablinks[i].className.replace(" active", "");
  }
  document.getElementById(tabName).style.display = "block";
  evt.currentTarget.className += " active";
}
</script>

<!-- Presentacion de la especie y los datos -->

<div style="font-family: Times; text-align: center;">
    <h2><i>Leucostethus jota</i></h2>
    <img src="{{ site.baseurl }}/images/especie_Leucostethus_jota.png" style="width:15cm;">
</div>
<br><br>

Los audios y tablas corresponden a la publicación:
<strong>Marín, C.M., C. Molina-Zuluaga, A. Restrepo, E.Cano & J.M. Daza.</strong> 2018. A new species of <i>Leucostethus</i> (Anura: Dendrobatidae) from the eastern versant of the Central Cordillera of Colombia with comments on the phylogenetic position of <i>Colostethus fraterdanieli</i>. <i>Zootaxa</i> 4461: 359--380. <a href="https://doi.org/10.11646/zootaxa.4461.3.3">https://doi.org/10.11646/zootaxa.4461.3.3</a>

Contribución por: <a href="mailto:marinc.carlosmario@gmail.com">Carlos M. Marin</a>, <a href="mailto:juanm.daza@udea.edu.co">Juan M. Daza</a>

<!-- Definicion de secciones -->

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'EspectroLejo')">Espectrograma</button>
  <button class="tablinks" onclick="openTab(event, 'tabLejo')">Tablas</button>
  <button class="tablinks" onclick="openTab(event, 'audLejo')">Audios</button>
</div>

<!-- Seccion espectrograma -->

<div id="EspectroLejo" class="tabcontent" style="text-align: center;">
  <video width="100%" height="auto" controls style="display: block; margin-left: auto; margin-right: auto;">
    <source src="{{ site.baseurl }}/Espectrograms/Leucostethus_jota.mp4" type="video/mp4">
    Tu navegador no soporta el elemento de video.
  </video>
  <br><br>
  <img src="{{ site.baseurl }}/images/espectrograma_Diasporus_anthrax.png" style="width:10cm; display: block; margin-left: auto; margin-right: auto;">
</div>

<!-- Seccion de tablas -->

<div id="tabLejo" class="tabcontent">
  <p>Descarga tabla de medidas <a href="https://bit.ly/3LUkN5s">aquí</a>.</p>
  <p>Descarga tabla selección RAVEN <a href="https://bit.ly/3LUkN5s">aquí</a>.</p>
</div>

<!-- Seccion de audios -->

<div id="audLejo" class="tabcontent">
  <div class="audio-container">
    <audio controls>
      <source src="{{ site.baseurl }}/Audios/Dendropsophus_phlebodes.wav" type="audio/wav">
      Tu navegador no soporta el elemento de audio.
    </audio>
  </div>
  <p>Audios disponibles <a href="https://bit.ly/3LUkN5s">aquí</a>.</p>
</div>

# Spectrogram Visualizer

Below is an audio file visualized as a spectrogram:

<div id="waveform"></div>
<div id="spectrogram"></div>

<button onclick="playPause()">Play/Pause</button>

<!-- Include the WaveSurfer.js library -->
<script src="https://unpkg.com/wavesurfer.js"></script>

<!-- Include the Spectrogram plugin -->
<script src="https://unpkg.com/wavesurfer.js/dist/plugin/wavesurfer.spectrogram.min.js"></script>

<!-- Create a new WaveSurfer instance and configure it -->
<script>
    var wavesurfer = WaveSurfer.create({
        container: '#waveform',
        waveColor: 'violet',
        progressColor: 'purple',
        backend: 'WebAudio',
        height: 128,
        plugins: [
            WaveSurfer.spectrogram.create({
                wavesurfer: wavesurfer,
                container: '#spectrogram',
                labels: true
            })
        ]
    });

    // Load an externally hosted audio file
    wavesurfer.load('Audios/Boana_boans.wav');

    // Play or pause the audio
    function playPause() {
        wavesurfer.playPause();
    }
</script>



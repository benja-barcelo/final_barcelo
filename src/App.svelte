<script>
  // Función para inicializar el componente de Flourish y tomar el script que nos permite hacer el scrolly gratis!
  import { onMount } from 'svelte';

  // Array para guardar la data de cada slide. Cambiar cada uno con el epígrafe específico para cada slide.
  const slides = [
    "¿Qué es un triple? En la NBA, un triple es un lanzamiento que otorga tres puntos cuando el jugador encesta desde detrás de la línea de tres puntos, situada a 7.24 metros del aro en su punto más alejado.",
    "Este tiro exige precisión, técnica y fuerza, siendo un elemento clave en las estrategias modernas.",
    "Stephen Curry, base de los Golden State Warriors, es considerado el mejor tirador de la historia de la NBA gracias a su precisión, rapidez y rango de tiro casi ilimitado.",
    "Su éxito se basa en una combinación de técnica impecable, movimientos constantes sin balón y una capacidad única para encestar triples en cualquier situación, ya sea en transición, bajo presión o desde distancias impensadas.",
    "Cuando su juego explotó en 2015, su estilo innovador y su eficacia desde el perímetro obligaron a los equipos a rediseñar estrategias ofensivas y defensivas, impulsando una era del baloncesto donde el triple se convirtió en el eje central del juego.",
    "En 2010, el primer año de Stephen en la NBA, el juego de la NBA era más balanceado, con ofensivas que distribuían los tiros entre la pintura, media distancia y triples. Los equipos dependían menos del tiro exterior, priorizando un enfoque más variado y físico en sus estrategias.",
    "Aquí se muestran los tiros realizados por su equipo, los Golden State Warriors, ese año, donde vemos una distribución pareja de los tiros.",
    "Sin embargo, en 2015, Curry tuvo una temporada en la que batió todos los récords con su habilidad del triple. Dominó la liga, ganando el campeonato, y siendo el mejor jugador durante todo el año, principalmente por sus tiros desde el exterior.",
    "Aquí se compara sus tendencias de tiros con las de Lebron James, su principal rival. Lebron es un jugador completo que cubre todas las zonas de la cancha. Steph, a diferencia de Lebron, abunda en la cantidad de triples encestados, mientras que James tiene una distribución más balanceada.",
    "Al comparar la cantidad de triples de cada uno, vemos que Steph realmente marcó la diferencia en comparación con Lebron, a quien le ganó las finales.",
    "Tras el éxito de Curry, los equipos convirtieron su forma de jugar, priorizando el tiro de 3 puntos. Las tendencias de tiros cambiaron, pareciendose a las de Curry",
    "Aquí están los tiros realizados por Golden State Warriors el año pasado, 2023.",
    "Al compararlo con como eran en 2010, se ve que la tendencia cambió hacia priorizar el triple, desde mayores distancias",
    "El juego se transformó al estilo de Curry, con abundancia en los triples para sumar más puntos.",
    "En 2010 los equipos tenían formas de jugar que representaban a la de Lebron James, tiros alrededor de las distintas zonas.",
    "Pero Steph Curry revolucionó el juego, para que si el tiro no es uno asegurado desde cerca del aro, entonces la mejor opción es sumar de a 3 puntos. Los equipos hoy usan juegos representativos a los de Stephen",

  ]

  function loadFlourishScrolly() {
    const script = document.createElement('script')
    script.src = "https://cdn.flourish.rocks/flourish-scrolly-v3.1.0.min.js"
    script.type = "text/javascript"
    script.onload = () => initFlourishScrolly()
    document.body.appendChild(script)
  }


  onMount(() => {
    loadFlourishScrolly()
  });
</script>

<section id="header">
  <img src="./public/images/NBA-Logo.png" alt="NBA Logo" class="logo">
  <h1 id="main_title">
    La evolución del triple en la NBA en la última década
  </h1>
</section>

<div class="texto_container">
  <p class="texto_parrafo">
    Esta visualización de los tiros de distintos equipos a través de los años en la NBA busca mostrar el impacto que tuvo Stephen Curry sobre las tendencias del deporte: </p>
</div>

<div class="texto_container">
  <h2 class="subtitulo"></h2>
  <p class="texto_parrafo">  </p>
</div>

<!-- Contenedor de la story de flourish (scrolly)-->
<div id="my-wrapper">
  <!-- Reemplazar el ID de jeemplo por el de la story propia -->
  <div class="flourish-embed" data-src="story/2727135"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/story/2727135/thumbnail" width="100%" alt="visualization" /></noscript></div>    
    <!-- <script src="https://public.flourish.studio/resources/embed.js"></script> -->

  <!-- Iteramos sobre las distintas slides del componente de Flourish -->
  {#each slides as slide, index}
    <p>
      {slide}
      <!-- svelte-ignore a11y-missing-content -->
      <a href={"#story/2727135/slide-" + (index + 1)}></a>
    </p>
  {/each}
</div>

<div class="final_container">
  <p class="final_parrafo">
    Visualzación realizada por Benjamín Barceló
  </p>
<img src="./public/images/ditella.jpg" alt="UTDT Logo" class="utdt-logo">

</div>

<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">


<style>

a {
  font-weight: 500;
  color: #646cff;
  text-decoration: inherit;
}
a:hover {
  color: #535bf2;
}


#my-wrapper {
  margin: 0px;
  max-width: 1280px;
}

#header {
  max-width: 800px;
  text-align: center;
  margin: 50px auto;
}
#main_title {
  font-size: 3em;
  line-height: 1.1;
}

.subtitulo {
  font-size: 1.5em;
  text-align: center;
}
.texto_container {
  max-width: 1000px;
  padding: 0 20px;
  margin: auto;
  margin-bottom: 100px;
  text-align: justify;
}
.texto_parrafo {
  margin: 50px auto;
}
.final_container {
  max-width: 1000px;
  padding: 0 20px;
  margin: auto;
  margin-bottom: 100px;
  text-align: center;
}
.final_parrafo {
  margin: 50px auto;
}
.logo {
  max-width: 200px; 
  height: auto;
}
.utdt-logo {
    margin-top: 0px; /* Espacio entre el texto y la imagen */
    max-width: 400px; /* Ajustar el tamaño de la imagen */
    height: auto; /* Mantener proporción */
  }
</style>
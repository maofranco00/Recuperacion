<template>
  <div id="app">

    <top-banner v-bind:idCarousel="['carousel1']" ></top-banner>

    <div class="container-fluid">

<!-- aquí se deberían cargar 4 películas que simulan las 4 noticias pero el hook no es el correcto -->
          <section-api></section-api>
        </div>

<!-- Esta es la tarjeta de miembros que nos piden pero al parecer estamos enviando las props de mala manera o con un nombre no correcro -->
    <div class="container-fluid">
      <div class="row justify-content-center mb-5">
        <div class="col mt-5" v-for="(item, index) of team" :key="index">
          <team-card :member="item"></team-card>
        </div>
      </div>
    </div>

    <page-footer></page-footer>
    <!-- <h1>{{ title }}</h1> -->
  </div>
</template>

<script>
import PageFooter from "./components/PageFooter.vue";
import TeamCard from "./components/TeamCard.vue";
import SectionApi from "./components/SectionApi.vue";
import TopBanner from './components/TopBanner.vue';

export default {
  name: "App",
  components: {
    PageFooter,
    TeamCard,
    SectionApi,
    TopBanner,
  },
  data(){
    return {
      title: "Vivo dentro de VUE",
      carousel1 : 'carousel1',
      // Esta es la definición del objeto team, el objeto contiene la info de cada miembro del equipo
      // Se esta enviando correctamente en el ciclo v-for pero las pruebas fallan
      // Al parecer tenemos un problema con la definición de los nombres de los atributos
      team: [
        {
          codigo: 1,
          nombre: "Integrante 1",
          descripcion:
            "1. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore omnis, laudantium tempore, provident corporis iure ex libero repellendus accusamus accusantium at voluptate excepturi voluptatem quis, illo modi exercitationem error consequatur.",
          rol: "Desarrollador backend",
          imagen: "https://placeimg.com/192/192/people",
        },
        {
          codigo: 2,
          nombre: "Integrante 2",
          descripcion:
            "2. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore omnis, laudantium tempore, provident corporis iure ex libero repellendus accusamus accusantium at voluptate excepturi voluptatem quis, illo modi exercitationem error consequatur.",
          rol: "Desarrollador backend",
          imagen: "https://placeimg.com/192/192/nature",
        },
        {
          codigo: 3,
          nombre: "Integrante 3",
          descripcion:
            "3. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore omnis, laudantium tempore, provident corporis iure ex libero repellendus accusamus accusantium at voluptate excepturi voluptatem quis, illo modi exercitationem error consequatur.",
          rol: "Desarrollador backend",
          imagen: "https://placeimg.com/192/192/architecture",
        },
        {
          codigo: 4,
          nombre: "Integrante 4",
          descripcion:
            "4. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore omnis, laudantium tempore, provident corporis iure ex libero repellendus accusamus accusantium at voluptate excepturi voluptatem quis, illo modi exercitationem error consequatur.",
          rol: "Desarrollador backend",
          imagen: "https://placeimg.com/192/192/animals",
        },
        {
          codigo: 5,
          nombre: "Integrante 5",
          descripcion:
            "5. Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore omnis, laudantium tempore, provident corporis iure ex libero repellendus accusamus accusantium at voluptate excepturi voluptatem quis, illo modi exercitationem error consequatur.",
          rol: "Desarrollador backend",
          imagen: "https://placeimg.com/192/192/any",
        },
      ],
    };
  },
};
</script>
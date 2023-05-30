<template>
  <main class="main">
    <title-block />
    <form-block @searhData="searhData" />
    <answer-block v-bind:answer="answer" />
  </main>
  <section class="section">
    <map-block v-bind:answer="answer" />
  </section>
</template>

<script>
import MapBlock from '@/components/MapBlock.vue';
import TitleBlock from '@/components/TitleBlock.vue';
import AnswerBlock from '@/components/AnswerBlock.vue';
import FormBlock from '@/components/FormBlock.vue';

export default {
  name: 'App',
  components: { MapBlock, TitleBlock, AnswerBlock, FormBlock },
  data() {
    return {
      answer: {
        query: '-',
        city: '-',
        isp: '-',
        country: ' ',
        zip: ' ',
        lat: 0,
        lon: 0,
      },
    };
  },
  methods: {
    async searhData(ipAddress) {
      try {
        const request = await fetch(
          `http://ip-api.com/json/${ipAddress}?fields=continent,country,regionName,city,zip,lat,lon,timezone,offset,isp,query`
        );
        const response = await request.json();
        this.answer = response;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@400;500;700&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

input,
button {
  font: inherit;
}

#app {
  font-family: 'Rubik', sans-serif;
  .main {
    position: relative;
    width: 100%;
    min-height: 30vh;

    display: flex;
    flex-direction: column;
    align-items: center;

    background-image: url('./assets/pattern-bg-mobile.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  .section {
    width: 100%;
    min-height: 70vh;
  }
  /* xs (<=543px) */
  @media (max-width: 575px) {
  }

  /* sm (>=576 и <=767) */
  @media (min-width: 576px) and (max-width: 767px) {
    .main {
      background-image: url('./assets/pattern-bg-desktop.png');
    }
  }

  /* md (>=768 и <=991) */
  @media (min-width: 768px) and (max-width: 991px) {
    .main {
      background-image: url('./assets/pattern-bg-desktop.png');
    }
  }

  /* lg (>=992 и <=1199) */
  @media (min-width: 992px) and (max-width: 1199px) {
    .main {
      background-image: url('./assets/pattern-bg-desktop.png');
    }
  }

  /* xl (>=1200) */
  @media (min-width: 1200px) {
    .main {
      background-image: url('./assets/pattern-bg-desktop.png');
    }
  }
}
</style>

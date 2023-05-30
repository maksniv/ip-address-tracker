<template>
  <yandex-map
    :coords="[answer.lat, answer.lon]"
    :zoom="10"
    :settings="settings"
    :behaviors="behaviors"
    :controls="controls"
  >
    <ymap-marker :coords="[answer.lat, answer.lon]" marker-id="123" />
  </yandex-map>
</template>

<script>
import { yandexMap, ymapMarker } from 'vue-yandex-maps';

export default {
  name: 'MapBlock',
  components: { yandexMap, ymapMarker },
  props: {
    answer: {},
  },
  data() {
    return {
      coords: [54, 39],
      behaviors: ['drag'],
      settings: {
        apiKey: '',
        lang: 'ru_RU',
        coordorder: 'latlong',
        version: '2.1',
      },
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.ymap-container {
  height: 100vh;
  width: 100%;
}
</style>

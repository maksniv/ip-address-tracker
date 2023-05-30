<template>
  <div class="answer-block">
    <div class="block">
      <div class="title">ip address</div>
      <div class="value">{{ answer.ip }}</div>
    </div>
    <div class="block">
      <div class="title">location</div>
      <div class="value">
        {{ answer.country_name + ' ' + answer.city + ' ' + answer.postal }}
      </div>
    </div>
    <div class="block">
      <div class="title">timezone</div>
      <div class="value">{{ getCurrentUTC(answer.utc_offset) }}</div>
    </div>
    <div class="block">
      <div class="title">isp</div>
      <div class="value">{{ answer.org }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AnswerBlock',
  props: {
    answer: {},
  },
  methods: {
    getCurrentUTC(time) {
      if (time === '-') {
        return '-';
      }
      const startString = time.substr(0, 3);
      const endString = time.substr(3, 4);

      return 'UTC' + startString + ':' + endString;
    },
  },
};
</script>

<style lang="scss">
@import '../assets/styles/variables.scss';

.answer-block {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  z-index: 1;

  width: 90%;
  max-width: 1110px;
  height: 22rem;

  position: absolute;
  bottom: -105%;

  background-color: $white;
  border-radius: 0.9rem;
  padding: 1rem;
  box-shadow: 7px 7px 20px $darkGrayColor;
  transition: all 0.2s ease-in;
  .block {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    .title {
      font-size: 10px;
      letter-spacing: 0.125rem;
      font-weight: 500;
      color: $darkGrayColor;
      text-align: center;
      text-transform: uppercase;
    }
    .value {
      font-size: 20px;
      font-weight: 700;
      color: $veryDarkgrayColor;
      text-transform: uppercase;
      text-align: center;
    }
  }
}

/* xs (<=543px) */
@media (max-width: 575px) {
}

/* sm (>=576 и <=767) */
@media (min-width: 576px) and (max-width: 767px) {
  .answer-block {
    bottom: -80%;
  }
}

/* md (>=768 и <=991) */
@media (min-width: 768px) and (max-width: 991px) {
  .answer-block {
    flex-direction: row;
    align-items: flex-start;

    min-height: 11rem;
    height: auto;

    bottom: -25%;
    .block {
      width: 25%;
      min-height: 60%;
      border-right: 2px solid $darkGrayColor;
      padding-left: 0.5rem;
      padding-right: 0.5rem;
      &:first-child {
        padding: none;
      }
      &:last-child {
        padding: none;
        border: none;
      }
      .title {
        font-size: 12px;
        text-align: left;
      }
      .value {
        font-size: 25px;
        text-align: left;
      }
    }
  }
}
/* lg (>=992 и <=1199) */
@media (min-width: 992px) and (max-width: 1199px) {
  .answer-block {
    flex-direction: row;
    align-items: flex-start;

    min-height: 11rem;
    height: auto;

    bottom: -25%;
    .block {
      width: 25%;
      min-height: 60%;
      border-right: 2px solid $darkGrayColor;
      padding-left: 1rem;
      padding-right: 1rem;
      &:last-child {
        border: none;
      }
      .title {
        font-size: 12px;
        text-align: left;
      }
      .value {
        font-size: 25px;
        text-align: left;
      }
    }
  }
}

/* xl (>=1200) */
@media (min-width: 1200px) {
  .answer-block {
    flex-direction: row;
    justify-content: center;

    height: auto;
    min-height: 11rem;

    bottom: -30%;
    .block {
      width: 25%;
      min-height: 60%;
      border-right: 2px solid $darkGrayColor;
      padding-left: 2rem;
      padding-right: 2rem;
      &:last-child {
        border: none;
      }
      .title {
        font-size: 12px;
        text-align: left;
      }
      .value {
        font-size: 25px;
        text-align: left;
      }
    }
  }
}
</style>

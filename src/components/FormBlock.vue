<template>
  <form @submit.prevent class="form">
    <input
      v-model="searhDataValue"
      type="text"
      class="input"
      placeholder="Search for any IP address"
    />
    <button type="submit" class="button" @click="searhData"></button>
  </form>
</template>

<script>
export default {
  name: 'FormBlock',
  data() {
    return {
      searhDataValue: '',
    };
  },
  methods: {
    searhData() {
      console.log(this.searhDataValue);
      this.$emit('searhData', this.searhDataValue);
      this.searhDataValue = '';
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/styles/variables.scss';
.form {
  margin-top: 2rem;
  width: 90%;
  max-width: 550px;
  height: auto;
  display: flex;
  justify-content: center;
  transition: all 0.2s ease-in;
  .input {
    width: 90%;
    height: 100%;
    border: none;
    outline: none;

    height: 3.5rem;
    padding: 0.375rem 1rem;
    font-size: 1rem;
    font-weight: 400;
    border-radius: 0.9rem 0% 0% 0.9rem;
    &:hover {
      cursor: pointer;
    }
    &::placeholder {
      color: $darkGrayColor;
    }
  }
  .button {
    color: white;
    background-color: $veryDarkgrayColor;
    border: none;

    width: 10%;
    height: 3.5rem;
    border-radius: 0% 0.9rem 0.9rem 0%;
    background-image: url('../assets/icon-arrow.svg');
    background-position: center;
    background-repeat: no-repeat;

    transition: all 0.2s ease-in;
    &:hover {
      transform: scale(1.03);
      cursor: pointer;
    }
  }
}
</style>

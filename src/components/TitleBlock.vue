<template>
  <h1 class="title">IP Address Tracker</h1>
</template>

<script>
export default {
  name: 'TitleBlock',
};
</script>

<style lang="scss" scoped>
.title {
  margin-top: 1.15rem;
  font-size: 25px;
  font-weight: 500;
  color: white;
}
/* xs (<=543px) */
@media (max-width: 575px) {
}

/* sm (>=576 и <=767) */
@media (min-width: 576px) and (max-width: 767px) {
}

/* md (>=768 и <=991) */
@media (min-width: 768px) and (max-width: 991px) {
  .title {
    margin-top: 2rem;
    font-size: 30px;
    color: white;
  }
}

/* lg (>=992 и <=1199) */
@media (min-width: 992px) and (max-width: 1199px) {
  .title {
    margin-top: 2rem;
    font-size: 30px;
    color: white;
  }
}

/* xl (>=1200) */
@media (min-width: 1200px) {
  .title {
    margin-top: 2rem;
    font-size: 30px;
    color: white;
  }
}
</style>

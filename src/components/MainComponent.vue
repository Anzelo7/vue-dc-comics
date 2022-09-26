<template>
  <main>
    <div class="container">
      <div class="container-item" v-for="card in cards" :key="card.series">
        <CardComponent :card="card" />
      </div>
    </div>
  </main>
</template>

<script>
import CardComponent from '@/components/CardComponent.vue';

export default {
  name: 'MainComponent',
  props: {
    cards: Array,
  },
  // props: ['cards'] // per prototipare
  components: {
    CardComponent,
  },
  mounted() {
    console.log(this.cards);
  },
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables';

.container {
  display: flex;
  flex-wrap: wrap;
}
.container-item {
  width: calc(100% / 6);
}

main {
  background-color: $bg-main;
  color: $color-main;
  padding: 50px 0px;
}
</style>
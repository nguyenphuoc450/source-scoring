<script setup>
import { computed } from 'vue';
import { useStore } from 'vuex';
import MatchItem from './MatchItem.vue';

const store = useStore()

const matchs = computed(() => {
  return store.getters.getMatchs
})

</script>

<template>
  <div class="match-list">
    <MatchItem v-for="item in matchs" :key="item.id" :data="item" />
  </div>
</template>

<style lang="scss" scoped>
.match-list {
  margin: 24px 0;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 16px;
}
</style>

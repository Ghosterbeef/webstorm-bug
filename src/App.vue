<template>
  {{ filtered }}
</template>

<script setup lang="ts">
import {computed, ref} from 'vue';

const array = ref<{a: number; b: number}[] | null>([
  {
    a: 1,
    b: 2,
  },
]);

const filtered = computed(() => {
  if (!array.value) {
    return [];
  }

  return array.value.filter((item) => item.a < item.b);
});
</script>

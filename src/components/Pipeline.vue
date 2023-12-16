<script setup>
import draggable from 'vuedraggable'
import { ref, defineProps, onMounted } from 'vue';
const props = defineProps(['cards'])

const cards = ref([])
onMounted(() => cards.value = props.cards)
</script>

<template>
  <draggable class="space-y-4" v-model="cards" group="cards" @start="drag = true" @end="drag = false" item-key="text">
    <template #item="{ element }">
      <div class="py-4 px-2">
        {{ element.text }}
      </div>
    </template>
  </draggable>
</template>

<style scoped></style>

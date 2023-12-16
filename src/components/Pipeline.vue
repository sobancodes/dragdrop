<script setup>
import draggable from 'vuedraggable'
import { ref, defineProps, onMounted } from 'vue';
const props = defineProps(['cards'])

const cards = ref([])
onMounted(() => cards.value = props.cards)
</script>

<template>
  <draggable class="space-y-2 text-sm h-full" v-model="cards" group="cards" @start="drag = true" @end="drag = false"
    item-key="text">
    <template #item="{ element }">
      <div class="rounded-md shadow-sm mx-2 p-4 bg-white text-gray-500">
        {{ element.text }}
      </div>
    </template>
  </draggable>
</template>

<style scoped></style>

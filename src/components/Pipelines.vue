<script setup>
// import Pipeline from './components/Pipeline.vue'
import draggable from 'vuedraggable'
import Pipeline from './Pipeline.vue';

import { ref } from 'vue'

const cards = ref([
  {
    text: 'Development',
    cards: [
      {
        id: 1,
        text: 'Complete code for blog post'
      },
      {
        id: 2,
        text: 'Complete blog',
      },
      {
        id: 3,
        text: 'Fix not able to drag parent pipeline',
      }
    ],
  },
  {
    text: 'SQA',
    cards: [
      {
        id: 4,
        text: 'Test code'
      },
      {
        id: 5,
        text: 'Prepare bug sheet',
      }
    ],
  }
])
</script>

<template>
  <div class="p-4">
    <div class="flex space-x-4">
      <div class="rounded-md min-h-[600px] w-[250px] max-w-[250px] bg-gray-50" v-for="card in cards" :key="card.id">
        <h3 class="p-2 font-semibold">
          {{ card.text }}
        </h3>
        <Pipeline :cards="card.cards" />
      </div>
    </div>
    <!-- <draggable class="flex space-x-4" v-model="cards" group="pipelines" @start="drag = true" @end="drag = false"
      item-key="text">
      <template #item="{ element }">
        <div class="font-semibold rounded-md shadow w-[250px] p-2">
          <h3>
            {{ element.text }}
          </h3>

          <Pipeline :cards="element.cards" />
        </div>
      </template>
    </draggable> -->
  </div>
</template>

<style scoped>
.buttons {
  margin-top: 35px;
}

.row-v {
  height: 150px;
  width: 200px;
}

.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}
</style>
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
        text: 'No Idea'
      },
      {
        id: 5,
        text: 'Again No Idea',
      }
    ],
  }
])
</script>

<template>
  <div class="p-4">
    <draggable class="flex space-x-4" v-model="cards" group="pipelines" @start="drag = true" @end="drag = false"
      item-key="text">
      <template #item="{ element }">
        <div class="font-semibold rounded-md shadow w-[250px] p-2">
          <h3>
            {{ element.text }}
          </h3>

          <Pipeline :cards="element.cards" />
        </div>
      </template>
    </draggable>
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
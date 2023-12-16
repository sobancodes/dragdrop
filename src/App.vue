<script setup>
import Pipelines from './components/Pipelines.vue'
import draggable from 'vuedraggable'
import { ref } from 'vue'

const array1 = ref([
  {
    id: 1,
    text: 'Basic example',
  },
  {
    id: 2,
    text: 'Two column example'
  },
  {
    id: 3,
    text: 'Kanban board'
  }
])

const array2 = ref([
  {
    id: 4,
    text: 'Prepare code',
  },
  {
    id: 5,
    text: 'Demonstrate prepared code'
  },
])
</script>

<template>
  <div class="p-4 flex space-x-3">
    <!-- <draggable class="space-y-2" v-model="array1" item-key="element">
      <template #item="{ element }">
        <div class="border rounded p-2 w-[250px]">
          {{ element.text }}
        </div>
      </template>
    </draggable>

    <draggable class="space-y-2" v-model="array2" item-key="element">
      <template #item="{ element }">
        <div class="border rounded p-2 w-[250px]">
          {{ element.text }}
        </div>
      </template>
    </draggable> -->
    <Pipelines />
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
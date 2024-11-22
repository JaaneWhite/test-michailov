<template>
  <div class="items-block">
    <div class="selected-items">
        <div class="item-tile" v-for="(item, index) in selectedItems" :key = "index">
          {{item.name}}
        </div>
    </div>
    <div class="all-items">
      <button class="item-tile" v-for="item in allItems" :key="item.id" @click="selectItem(item)">
        {{item.name}}
      </button>
    </div>
  </div>
</template>

<script setup>
import {reactive} from "vue";

const selectedItems = reactive([]);
const allItems = reactive([
    {
      "id": 1,
      "name": "Shoes 1"
    },
    {
      "id": 2,
      "name": "Shoes 2"
    },
    {
      "id": 3,
      "name": "Shoes 3"
    },
    {
      "id": 4,
      "name": "Shoes 4"
    },
    {
      "id": 5,
      "name": "T-shirt 1"
    },
    {
      "id": 6,
      "name": "T-shirt 2"
    },
    {
      "id": 7,
      "name": "T-shirt 3"
    },
    {
      "id": 8,
      "name": "T-shirt 4"
    }
]);
function selectItem(item) {
  if (selectedItems.length >= 6) {
    selectedItems.shift()
  }
  selectedItems.push(item);
}
</script>

<style scoped>

</style>
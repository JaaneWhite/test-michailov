<template>
  <div class="items-block">
    <div class="selected-items">
      <div class="item">
        {{selectedItem.name}}
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

const selectedItem = reactive({
  id: '',
  name: ''
});
const allItems = reactive([
  {
    "id": 11,
    "name": "Jacket 1"
  },
  {
    "id": 12,
    "name": "Jacket 2"
  },
  {
    "id": 13,
    "name": "Jacket 3"
  },
  {
    "id": 14,
    "name": "Jacket 4"
  },
  {
    "id": 15,
    "name": "Hoodie 1"
  },
  {
    "id": 16,
    "name": "Hoodie 2"
  },
  {
    "id": 17,
    "name": "Hoodie 3"
  },
  {
    "id": 18,
    "name": "Hoodie 4"
  }
]);
function selectItem(item) {
  selectedItem.id = item.id
  selectedItem.name = item.name
}
</script>


<style scoped>

</style>
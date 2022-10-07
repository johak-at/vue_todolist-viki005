<script setup>
import { ref, computed } from "vue";

const list = ref([]);

const newitem = ref("");
const filter = ref("");

function additem() {
  list.value.push(newitem.value);
  newitem.value = "";
}

function deleteitem(index) {
  list.value.splice(index, 1);
}
</script>

<!-- create a todolist with vue where i can delete items -->

<template>
  <div>
    <input @keyup.enter="additem" type="text" v-model="newitem" />
    <button @click="additem">Add Item</button><br />

    <ul>
      <li v-for="(item, index) in list" :key="item">
        {{ item }}
        <button @click="deleteitem(index)">X</button>
      </li>
    </ul>
  </div>
</template>

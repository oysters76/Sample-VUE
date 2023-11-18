<script setup lang="ts">
import { ref } from 'vue';


const listvalue = ref("");
const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
items.value.push({message:"test"})

function enterValue(event:Event){
 items.value.push({message:listvalue.value})
 listvalue.value = "";
}

</script>

<template>
  <input type="text" id="textbox" v-model="listvalue">
  <label>The value is : {{ listvalue }}</label>
  <button @click="enterValue">Enter</button>
  <ul>
    <li v-for="item in items">
      {{ item.message }}
    </li>
  </ul>
</template>
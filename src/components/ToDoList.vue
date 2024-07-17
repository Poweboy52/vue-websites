<script setup>
import { ref } from "vue"

const list = ref([
  { todo:"Get milk", done: false, id: 1231231 },
  { todo:"Get eggs", done: false, id: 23123891},
  { todo:"Get peanut butter", done: false, id: 183213281 },
  { todo:"Get ham", done: false, id: 1239193281 },
  { todo:"Get bread", done: false, id: 18237198723 }
])

function handleChange(done, id) {
  // Array methods, list.value is an array, you need to mutate array in place and return an array with a different done value
  // (argument) => return_value 
  // const myItem = list.value.find((item) => item.id === id) 

  // method one (DONE)
  // find index of item that needs to change
  // index into list.value[index] and change done

  // const index = list.value.findIndex((item) => item.id === id)
  // list.value[index].done = !done

  // method two
  // loop over all items
  // Remove unused assignment
  // Remove unused console.log

  list.value.map((item) => { 
    // if id matches, return item but with a modified done state (DONE)
    // if item does not match, just return item (DONE)

    if (item.id === id) {
      const itemTemp = item
      itemTemp.done = !done
      return itemTemp
    }

    return item
  })
}
</script>

<template>
<div>
  <!-- <pre>{{ list }}</pre> -->
  <h1>My to do list</h1>
    <ul>
      <template v-for="item in list">
        <li v-if="!item.done">
          <p>{{ item.todo }}</p>
          <input type="checkbox" :checked="item.done" @change="handleChange(item.done, item.id)"/>
        </li>
      </template>
    </ul>
</div>

<!--
Part 1 counter
<div>
  <button v-if="count > 0" @click="count = count - 1">-</button>
  <p>{{ count }}</p>
  <button v-if="count < 10" @click="count = count + 1">+</button>
</div>
-->
</template>

<style scoped></style>

<template>
  <div>
    <HelloWorld :msg="msg" :person="person"/>
  </div>

</template>

<script setup>
import { ref } from "vue"
import HelloWorld from './components/HelloWorld.vue';

const msg = ref("hi")
const person = ref("John")
</script>
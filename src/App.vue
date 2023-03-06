
<script setup>

import {ref} from 'vue';
const notes = ref([]);

const addNote = ()=>{
  notes.value.push({
    id : notes.value.length+1,
    background : '#'+ Math.floor(Math.random()*16777215).toString(16)
  });
}
const copy = ()=>{
      this.$refs.myinput.focus();
      document.execCommand('copy');
}
</script>

<template>
  <header>
   
  </header>

  <main class="container text-center mt-5 ">
    <div class="row">
      <h1>Colors Generator</h1>
      <button type="button" class="btn btn-success" @click="addNote">Act new Color</button>
    </div>


<div class="row ms-2">
  <div  v-for="note in notes" :key="note.id"  class="col-2 card  mt-4 ms-2" style="min-width: 18rem;cursor: pointer;" :style="{backgroundColor:note.background}">
  <div class="card-body text-black ">
    <p class="card-text" @click="copy">{{ note.background}}</p>
  </div>
 </div>

</div>
  </main>
</template>

<style scoped>

</style>

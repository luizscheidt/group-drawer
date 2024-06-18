<script setup>
import { ref } from 'vue';

const teams = [
  "abalo",
  "after",
  "atura",
  "baile",
  "batiza",
  "bond james bond",
  "brinde",
  "bronca",
  "broxa",
  "cartel",
  "camarote",
  "delirio",
  "desfecho",
  "diretoria",
  "dose",
  "encontro",
]

const groupA = ref([])
const groupB = ref([])
const groupC = ref([])
const groupD = ref([])

let clickCount = ref(0)

function addTeam() {
  const randomTeam = Math.floor(Math.random() * teams.length)
  if ((clickCount.value) % 4 === 0){
    groupA.value.push(teams[randomTeam])
  } else {
    if((clickCount.value) % 4 === 1){
      groupB.value.push(teams[randomTeam])
    } else {
    if((clickCount.value) % 4 === 2){
      groupC.value.push(teams[randomTeam])
    } else {
      groupD.value.push(teams[randomTeam])
  }}}
  teams.splice(randomTeam, 1)
  clickCount.value++
  }
 

</script>

<template>
  <div class="row">
    <div class="card" style="width: 30rem; ">
      <div class="card-header">
          Grupo A
        </div>
        <ul class="list-group list-group-flush">
          <!-- <li class="list-group-item" v-if="groupA.length === 0">Teams</li> -->
          <li class="list-group-item" v-for="team in groupA"> {{ team }}</li>
        </ul>
      </div>

      <div class="card" style="width: 30rem; ">
      <div class="card-header">
          Grupo B
        </div>
        <ul class="list-group list-group-flush">
          <!-- <li class="list-group-item" v-if="groupB.length === 0">Teams</li> -->
          <li class="list-group-item" v-for="team in groupB"> {{ team }}</li>
        </ul>
      </div>
      </div>

      <div class="row">
        <button @click="addTeam" class="draw-button"> <img src="/Users/lipe/Downloads/LOGO CC LEGENDS.png" alt="logo" class="logo"></button>
      </div>

      <div class="row">
      <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Grupo C
        </div>
        <ul class="list-group list-group-flush">
          <!-- <li class="list-group-item" v-if="groupC.length === 0">Teams</li> -->
          <li class="list-group-item" v-for="team in groupC"> {{ team }}</li>
        </ul>
      </div>


      <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Grupo D
        </div>
        <ul class="list-group list-group-flush">
          <!-- <li class="list-group-item" v-if="groupD.length === 0">Teams</li> -->
          <li class="list-group-item" v-for="team in groupD"> {{ team }}</li>
        </ul>
      </div>
    </div>
    
    <span> {{ teams.join(", ") }}</span>

</template>

<style scoped>

.card {
  background-color: rgb(37, 37, 37);
  color: black;
  height: 260px;
  margin: 10px;
}

.card-header{
  background-color: #D4AF37;
}

.list-group-item {
  color: #D4AF37;
  background-color: rgb(50, 50, 50);
}

.logo{
  height: 150px;
  width: 150px;
}

.draw-button {
  background-color: black;
}

.draw-button:hover {
  border: unset;
}


</style>

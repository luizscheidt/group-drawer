<script setup>
import { ref } from 'vue';

const teams = [
  "abalo",
  "atura",
  "baile",
  "batiza",
  "bond james bond",
  "brinde",
  "bronca",
  "broxa",
  "cartel",
  "camarote",
  "chora",
  "delirio",
  "desfecho",
  "diretoria",
  "dose",
  "encontro"
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
  <header style="margin-bottom: 30px;">
    <h1>CATARINENSE LEGENDS</h1>
    <span> {{ teams.join(", ") }}</span>

    <div>
      <button @click="addTeam" class="btn btn-lg btn-info" style="margin-top: 15px;">SORTEAR</button>
    </div>
  </header>
    
  <div class="row groups">
    <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Group A
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item" v-if="groupA.length === 0">Teams</li>
          <li class="list-group-item" v-else v-for="team in groupA"> {{ team }}</li>
        </ul>
      </div>

      <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Group B
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item" v-if="groupB.length === 0">Teams</li>
          <li class="list-group-item" v-else v-for="team in groupB"> {{ team }}</li>
        </ul>
      </div>

      <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Group C
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item" v-if="groupC.length === 0">Teams</li>
          <li class="list-group-item" v-else v-for="team in groupC"> {{ team }}</li>
        </ul>
      </div>

      <div class="card" style="width: 30rem; margin-top: 20px;">
      <div class="card-header">
          Group D
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item" v-if="groupD.length === 0">Teams</li>
          <li class="list-group-item" v-else v-for="team in groupD"> {{ team }}</li>
        </ul>
      </div>
    </div>
    


</template>

<style scoped>
.groups{
  display: flex;
  justify-content: space-around;
  align-items: space-around;
}


</style>

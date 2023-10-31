<template>
  <h1 >Heures de travail</h1>
  <form v-on:submit.prevent="getWorkingTimes">
    <input type="text" v-model="startDate" placeholder="Date de début">
    <input type="text" v-model="endDate" placeholder="Date de début">
    <button>Rechercher</button>
  </form>
  <div v-if="workingTimes.length > 0" >
    <p v-for="workingTime in workingTimes" :key="workingTime.id"> Debut: {{ workingTime.start }} -- Fin:{{ workingTime.start }}</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "WorkingTimesComposant",

  data() {
    return {
      workingTimes: [],
      userID: "1",
      startDate: "",
      endDate: ""
    };
  },

  methods: {
    getWorkingTimes() {
      axios.get(`http://localhost:4000/api/workingtimes/${this.userID}`, {
        params: {
        start: this.startDate,
        end: this.endDate
      }
      }).then(response => {
        this.workingTimes = response.data.data;
        console.log(this.workingTimes[0]);
      })
    }
  }
}


</script>

<style>

</style>

<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <WorkingTimes />
  <UserComponent />
</template>

<script>
import WorkingTimes from './components/WorkingTimes.vue';
import UserComponent from './components/UserComponent.vue';


export default {
  name: 'App',
  components: {
    WorkingTimes, UserComponent
  }
}
</script>
<style>
</style>

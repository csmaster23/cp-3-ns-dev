<template>
  <div>
    <h1>Customize Your Allstar Profile</h1>
    <h2>{{ name }}</h2>
    <img v-bind:src="imagePath"/>
  </div>
</template>

<script>
 export default {
   name: 'Profile',
   data () {
     return {
       name: 'Big Arm Brock',
       imagePath: '/static/images/road-runner.jpg'
     }
   }
 }
</script>

<style scoped>
 img {
     max-width: 500px;
 }
</style>
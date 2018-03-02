<template>
    <div id="app">
      <app-header></app-header>
      <router-view/>
      <br><br><br>
      <div class="container">
        <div class="row">
          <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12" style="background-color: #1E8BFF">
          <a style="color: white " href="https://github.com/csmaster23/cp-3-ns-dev.git">GitHub</a>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
 import AppHeader from './components/AppHeader.vue'
 export default {
     name: 'App',
     components: { AppHeader }
 }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
ss

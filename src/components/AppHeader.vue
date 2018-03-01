<template>
    <nav>
    <label for="show-menu" class="show-menu">Show Menu</label>
    <input type="checkbox" id="show-menu" role="button">
    <div class="container">
    <div class="row">
       
        <div id="menu" class="col-lg-10 col-md-10 col-sm-10 col-xs-10">
        
        <router-link to="/">Home</router-link>
        <router-link to="/profile">&nbsp Profile</router-link>

        </div>
        <div id="login" class="col-lg-2 col-md-2 col-sm-2 col-xs-2">
            <button type="button" class="btn btn-primary">Login</button>
        </div>

    </div>
    <hr>
    </div>   
    </nav>
    
</template>

<script>
 export default {
     name: 'AppHeader'
 }
</script>

<style scoped>
 /*Strip the ul of padding and list styling*/
 .clear {
     float: clear;
 }
 nav {
     display: grid;
 }
 ul {
     list-style-type:none;
     margin:0;
     padding:0;
 }

 /*Create a horizontal list with spacing*/
 li {
     display:inline-block;
     float: left;
     margin-right: 1px;
 }
 /*Style for menu links*/
 li a {
     display:block;
     margin-right: 20px;
     height: 50px;
     text-align: center;
     line-height: 50px;
     color: black;
 }
 /*Active color*/
 a.active {
    color: gray;
 }

 /*Hover state for top level links*/
 :hover a {
    text-decoration: none;

 }
 /*Style 'show menu' label button and hide it by default*/
 .show-menu {
     text-decoration: none;
     color: black;
     background: #FF5035;
     text-align: center;
     padding: 10px 0;
     display: none;
 }
 /*Hide checkbox*/
 input[type=checkbox]{
     display: none;
 }
 /*Show menu when invisible checkbox is checked*/
 input[type=checkbox]:checked ~ #menu{
     display: block;
 }

 #menu {
    text-align: left;
    text-decoration: none;
    color: black;

 }

 #login {
    text-align: right;
    text-decoration: none;
    color: black;
    font-size: 3vh;
 }

 a {
    color: black;
    font-size: 3vh;
 }

</style>
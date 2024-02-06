<template>
  <router-view />
</template>

<script>


  export default {
    name: 'App',
  
}
</script>




<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #313c47;
  font-family: Kanit, Prompt;
}

* {
    margin: 0;
    padding: 0;
}

.menu {
    background-color: rgb(243, 152, 4);
    overflow: hidden;
    

}

.menu a {
    color: white;
    font-size: 20px;
    text-decoration: none;
    float: left;
    margin: 10px 15px;
    box-sizing: border-box;
    padding: 5px;
}

.menu a:hover {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}

.menu a:focus {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}

.menu router-link a:focus {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}


.rtx{
  text-decoration: none;
}

img.logo{
  width: 250px;
}

.container{
  width: 100%;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 20px;
  border: 1px solid black;
  border-radius: 5px;
  background-color: rgba(178, 201, 138, 0.635);
  border: 3px solid orange;
  padding: 15px;

}



</style>

<template>
  <div class="upperApp">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>
</div>
</template>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height:100%;
  background-color: rgb(255, 45, 160);

}
html,body{
  height: 100%;
  width: 100%;
  background-color:rgb(45, 255, 160);
  margin:0;
}
  .upperApp{
    background-color: rgb(255, 255, 8);
  }
nav {
  
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

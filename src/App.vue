<template>
  <div id="app">
    <div id="nav">
      <router-link class="logo" to="/">RecipeBook</router-link>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  background-color: #f2f2f2;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
}
@media (max-width: 1240px) {
  .container {
    max-width: 1060px;
  }
}
@media (max-width: 1100px) {
  .container {
    max-width: 960px;
  }
}
@media (max-width: 980px) {
  .container {
    max-width: 90%;
  }
}
#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  background: #fff;
  margin-bottom: 40px;
  box-shadow: 0px 0px 3px 2px rgba(44, 62, 80, 0.3);
  display: flex;
  align-items: center;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  font-size: 18px;
  margin-right: 20px;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
#nav a.logo {
  margin: 0 20px 0 0;
  color: #2c3e50;
  font-size: 2rem;
  text-decoration: none;
}
#nav a:hover {
  text-decoration: underline;
}

.button {
  box-sizing: border-box;
  color: rgb(30, 160, 30);
  border: 1px solid #fff;
  background: #fff;
  padding: 5px 10px;
  cursor: pointer;
  font-weight: bold;
  font-size: 20px;
  transition: 0.4s;
  border-radius: 3px;
  margin-right: 8px;
  margin-bottom: 8px;
}
.button:focus,
.button:active {
  box-shadow: 0 0 1px 3px rgb(149, 249, 149);
  outline: none;
}
.button.button--secondary {
  color: #fff;
  background: none;
}
.button:hover {
  color: #fff;
  border-color: rgb(17, 82, 17);
  background: rgb(17, 82, 17);
  transform: translateY(-4px);
  box-shadow: 0px 5px 15px 2px rgba(44, 62, 80, 0.3);
}
.button.button.button--secondary:hover {
  background: #fff;
  border-color: #fff;
  color: rgb(30, 160, 30);
}
</style>

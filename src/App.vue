<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
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
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
}
#nav a.router-link-exact-active {
  color: #42b983;
}

.bottom {
  padding: 16px;
  background: rgb(30, 160, 30);
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
  color: #2c3e50;
  border-color: rgb(149, 249, 149);
  background: rgb(149, 249, 149);
  transform: translateY(-4px);
  box-shadow: 0px 5px 15px 2px rgba(44, 62, 80, 0.3);
}
.button.button.button--secondary:hover {
  background: #fff;
  border-color: #fff;
  color: rgb(30, 160, 30);
}
</style>

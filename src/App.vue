<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.btn {
  background: #42b983;
  border: 1px solid #42b983;
  border-radius: 5px;
  color: #ffffff;
  cursor: pointer;
  font-size: 14px;
  text-decoration: none;
  padding: 8px 12px;
  margin: 2px 7px;
}

.input {
  border: 1px solid #2c3e50;
  border-radius: 5px;
  font-size: 14px;
  padding: 8px 12px;
  margin: 2px 7px;
}
</style>

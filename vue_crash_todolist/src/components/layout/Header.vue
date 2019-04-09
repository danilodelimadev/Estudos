<template>
  <header class="header">
    <h1>TodoList</h1>
      <div id="nav">
        <router-link to="/">Home</router-link>|
        <router-link to="/about">About</router-link>
    </div>
  </header>
</template>


<script>
export default {
  name: "Header",

  }

</script>


<style scoped>

.header {
  background: #333;
  color: #fff;
  margin-bottom: 20px;
  height: 80px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.header a{
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}

</style>

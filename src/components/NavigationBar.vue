<template>
  <div id="nav">
    <div class="nav-logo">Logo</div>
    <ul class="nav-links">
      <li><a href="#">Dashboard</a></li>
      <li><a href="#">Products</a></li>
      <li><a href="#">Cart</a></li>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
a:-webkit-any-link {
  text-decoration: none;
}
#nav {
  height: 30px;
  padding-top: 15px;
  background-color: aquamarine;
  border-bottom: black solid 1px;
}
.nav-logo {
  float: left;
  margin-left: 30px;
}
.nav-links {
  float: right;
  width: 20%;
  margin: 0 5px;
  display: flex;
  justify-content: space-evenly;
  right: 0;
}
.nav-links li {
  list-style: none;
}
</style>
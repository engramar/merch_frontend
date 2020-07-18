<template>
  <div id="nav" class="nav">
    <!--
    <img :src="require(`@/assets/cs_logo.png`)" height="100px" width="50px" />
    -->
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 10px;
}
.nav > .brand {
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
  font-size: 1.5em;
  color: #53708b;
  text-decoration: none;
}
.nav .nav-item {
  box-sizing: border-box;
  margin: 5 10px;
  color: rgba(0, 0, 0, 0.5);
  text-decoration: none;
}
.nav .nav-item.router-link-exact-active {
  color: #53708b;
  border-bottom: solid 2px #53708b;
}
</style>

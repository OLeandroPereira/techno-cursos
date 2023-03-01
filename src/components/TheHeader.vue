<template>
  <header>
    <nav>
      <div class="logo">
        <router-link to="/">Tech Invest</router-link>
      </div>
      <ul>
        <li>
          <router-link to="/cursos">Cursos</router-link>
        </li>
        <li>
          <router-link to="/contato">Contato</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>


<script>
export default {
  name: "TheHeader"
}
</script>

<style scoped>
header {
  background: black;
}

header a {
  color: rgb(255, 255, 255);
}

header a:hover {
  transition: 0.5s ease all;
  color: rgb(10, 240, 244);
}

a.router-link-active {
  color: rgb(10, 240, 244);
 }

 nav {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  align-content: space-between;
  padding: 20px;
}

.logo {
  flex: 1;
}

.logo a {
  color: white;
  font-size: 1.rem;
}

ul li {
  display: inline-block;
}

li a {
  padding: 0 10px;
}

</style>
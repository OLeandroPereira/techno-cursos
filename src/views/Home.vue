<template>
<div>
  <div v-if="loading">
    <PageLoading/>
  </div>
  <transition>
    <div v-if="api" class="conteudo">
      <div>
        <h1>{{ api.titulo }}</h1>
        <p>{{ api.descricao }}</p>
        <router-link class="btn-cursos" tag="button" to="/cursos">Vídeos Gratuítos</router-link>
        <div>
          <h2>Avaliações</h2>
          <ul>
            <li v-for="avaliacao in api.avaliacoes" :key="avaliacao.name">
              <h4 class="names">{{ avaliacao.nome }}</h4>
              <p>{{ avaliacao.descricao }}</p>
            </li>
          </ul>
        </div>
      </div>
      <img src="@/assets/OIP.jpeg" alt="Aprenda Web Design" />
    </div>
  </transition>
</div>
</template>


<script>
import fetchData from "@/mixins/fetchData.js";

export default {
  name: "HomePage",
  mixins: [fetchData],
  created() {
    this.fetchData("/home");
  }
};
</script>

<style scoped>
body {
  background: black;
}

h1 {
  color: rgb(10, 240, 244);;
}
.btn-cursos {
  border: none;
  background: rgb(211, 218, 219);
  border-radius: 4px;
  color: rgb(0, 0, 0);
  font-weight: bold;
  cursor: pointer;
  padding: 15px 40px;
  font-size: 1rem;
  margin-top: 10px;
  margin-bottom: 40px;
  font-family: "Avenir", Arial, Helvetica, sans-serif ;
}
.btn-cursos:hover {
  transition: 0.7s ease-in-out all;
  background-color: rgb(10, 240, 244);
  transition: 0.5s ease all;
}

.names{
  color: rgb(10, 240, 244);
  margin-bottom: -10px;
}
</style>
  


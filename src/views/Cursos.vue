<template>
  <div>
    <div v-if="loading">
      <PageLoading />
    </div>
    <transition>
      <div v-if="api" class="conteudo">
        <div>
          <h1>{{ api.titulo }}</h1>
          <p>{{ api.descricao }}</p>
        </div>
        <ul class="cursos-lista">
          <li v-for="curso in api.cursos" :key="curso.id">
            <h2>
              <router-link class="title" :to="{ name: 'curso', params: { curso: curso.id } }"
                >{{ curso.nome }} - {{ curso.totalAulas }} aulas |
                {{ curso.horas }} horas
              </router-link>
            </h2>
            <p>{{ curso.descricao }}</p>
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<script>
import fetchData from "@/mixins/fetchData.js";

export default {
  name: "CursosPage",
  mixins: [fetchData],
  created() {
    this.fetchData("/cursos");
  },
};
</script>

<style>
 html, body {
  height: 100%;
 }

 body {
  min-height: 100%;
  margin: 0px;
 }


.cursos-lista li {
  margin-bottom: 40px;
  background: rgb(7, 7, 7);
  padding: 15px;
  border-radius: 5px;
}

.title:hover {
  transition: 0.5s ease all;
  color: rgb(10, 240, 244);
}

</style>

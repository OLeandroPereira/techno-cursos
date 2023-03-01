<template>
  <div>
    <div v-if="loading">
      <PageLoading />
    </div>
    <transition>
      <div v-if="api" class="conteudo">
        <div>
          <h1>{{ api.nome }}</h1>
          <p>{{ api.descricao }}</p>
          <h2>Aulas</h2>
          <ul class="aulas">
            <li v-for="aula in api.aulas" :key="aula.id">
              <router-link :to="{ name: 'aula', params: { aula: aula.id } }">{{
                aula.nome
              }}</router-link>
            </li>
          </ul>
        </div>
        <router-view></router-view>
      </div>
    </transition>
  </div>
</template>

<script>
import fetchData from "@/mixins/fetchData.js";

export default {
  name: "CursoPage",
  props: ["curso"],
  mixins: [fetchData],
  created() {
    this.fetchData(`/curso/${this.curso}`);
  },
};
</script>

<style>
.aulas li a {
  display: block;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
  background: rgb(240, 236, 233);
  color: black;
  padding: 20px;
  margin-bottom: 10px;
  border-radius: 4px;
}

.aulas li a:hover {
  transition: 0.5s ease-in-out;
  background-color: rgb(10, 240, 244);
}

.aulas li a.router-link-active {
  background: rgb(10, 240, 244);
  color: rgb(68, 64, 64);
}
</style>

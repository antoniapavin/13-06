<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_time: "",
      times: [
        { id: "d2a89ae6-e7fa-11ec-8fea-0242ac120002", nome: "Time 1" },
        { id: "ccd84170-e7fa-11ec-8fea-0242ac120002", nome: "Time 2" },
        { id: "ae3c5404-e7fa-11ec-8fea-0242ac120002", nome: "Time 3" },
        { id: "b49afb84-e7fa-11ec-8fea-0242ac120002", nome: "Time 4" },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_time !== ""){
        const novo_id = uuid();
        this.times.push({
          id: novo_id,
          nome: this.novo_time,
        });
        this.novo_time = "";
      }
    },
    excluir(time){
      const indice = this.times.indexOf(time);
      this.times.splice(indice, 1);
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" @keyup.enter="salvar" />
      <button @click="salvar">salvar</button>
    </div>

    <div class="list-itens">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.nome }}</td>
            <td>
              <button>Editar</button>
              <button @click="excluir(time)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style></style>

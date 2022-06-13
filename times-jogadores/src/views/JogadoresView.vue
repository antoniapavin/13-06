<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_jogador: "",
      novo_time: "",
      jogadores: [
        {id: "385b2c1e-ae1d-4fc5-a3d9-7580ef07e298", name: "Jogador 1", idade: "X", timeid: "1", acoes:"?"  },
        {id: "a5df43ca-e7fa-11ec-8fea-0242ac120002", name: "Jogador 2", idade: "X", timeid: "1", acoes:"?"  },
        {id: "ae3c5404-e7fa-11ec-8fea-0242ac120002", name: "Jogador 3", idade: "X", timeid: "2", acoes:"?"  },
        {id: "b49afb84-e7fa-11ec-8fea-0242ac120002", name: "Jogador 4", idade: "X", timeid: "4", acoes:"?"  },
      ],
    };
  },
  methods: {
    salvar() {
      if(this.novo_jogador !== ""){
        const novo_id = uuid();
        this.jogadores.push({
          id:novo_id,
          name: this.novo_jogador,
          timeid: this.novo_time,
        });
        this.novo_jogador = "";
        this.novo_time = "";
      }
    },
    excluir(jogador){
      const indice = this.jogadores.indexOf(jogador);
      this.jogadores.splice(indice, 1);
    }
  },
};
</script>
<template>
 <div class="container">
  <div class="title">
    <h2>Gerenciamento de jogadores</h2>
  </div>
  <div class="form-input">
    <input type="text" placeholder="Nome" v-model="novo_jogador" @keyup.enter="salvar"> 
    <input type="text" placeholder="Time" v-model="novo_time" @keyup.enter="salvar">
    <button @click="salvar"> salvar</button>
  </div>
  
  <div class="list-itens">
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Nome</th>
          <th>Idade</th>
          <th>Time ID</th>
          <th>Ações</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="jogador in jogadores" :key="jogador.id">
          <td>{{jogador.id}}</td>
          <td>{{jogador.name}}</td>
          <td>{{jogador.idade}}</td>
          <td>{{jogador.timeid}}</td>
          <td>
            <button>Editar</button>
            <button @click="excluir(jogador)">Excluir</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
</template>
<style scoped>

</style>
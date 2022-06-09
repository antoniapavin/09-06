<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_time: "",
      times: [
        { id: "d2a89ae6-e7fa-11ec-8fea-0242ac120002", name: "Time 1" },
        { id: "ccd84170-e7fa-11ec-8fea-0242ac120002", name: "Time 2" },
        { id: "ae3c5404-e7fa-11ec-8fea-0242ac120002", name: "Time 3" },
        { id: "b49afb84-e7fa-11ec-8fea-0242ac120002", name: "Time 4" },
      ],
    };
  },
  methods: {
    salvar() {
      const novo_id = uuid();
      this.times.push({
        id: novo_id,
        name: this.novo_time,
      });
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
      <input type="text" v-model="novo_time" />
      <button @click="salvar">salvar</button>
    </div>
    {{ times }}
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
            <td>{{ time.name }}</td>
            <td>???</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style></style>

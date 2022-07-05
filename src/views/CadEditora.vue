<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      Id: "",
      Telefone: "",
      Nome: "",
      Site: "",
      editoras: [],
    };
  },
  methods: {
    salvar() {
      if (this.Id !== "") {
        const novo_id = uuid();
        this.editoras.push({
          id: novo_id,
          Id: this.Id,
          Telefone: this.Telefone,
          Nome: this.Nome,
          Site: this.Site,
        });
        this.Id = "";
        this.Telefone = "";
        this.Nome = "";
        this.Site = "";
      }
    },
    excluir(editora) {
      const indice = this.editoras.indexOf(editora);
      this.editoras.splice(indice, 1);
    },
    alerta() {
      alert("Ok!");
    },
  },
};
</script>
<template>
  <div class="editora">
    <label for="">Editora</label>
  </div>
  <router-link to="/cadastro">
    <button>←VOLTAR</button>
  </router-link>
  <div class="cadastro">
    <table>
      <thead>
        <tr>
          <td>Id</td>
          <td>Nome</td>
          <td>Site</td>
          <td>Telefone</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="editora in editoras" :key="editora.id">
          <td>{{ editora.Id }}</td>
          <td>{{ editora.Nome }}</td>
          <td>{{ editora.Site }}</td>
          <td>{{ editora.Telefone }}</td>

          <td>
            <button class="btnedit" @click="alerta(editora)">Editar</button>
            <button class="btnexcluir" @click="excluir(editora)">
              Excluir
            </button>
          </td>
        </tr>
      </tbody>
    </table>
    <input
      class="pesq"
      type="text"
      placeholder="Id"
      v-model="Id"
      @keyup.enter="salvar"
    />
    <input
      class="pesq2"
      type="text"
      placeholder="Nome"
      v-model="Nome"
      @keyup.enter="salvar"
    />
    <input
      class="pesq3"
      type="text"
      placeholder="Site"
      v-model="Site"
      @keyup.enter="salvar"
    />
    <input
      class="pesq4"
      type="text"
      placeholder="Telefone"
      v-model="Telefone"
      @keyup.enter="salvar"
    />
    <button @click="salvar" class="btncad">OK</button>
  </div>
</template>
<style scoped>
.editora {
  position: absolute;
  width: 920px;
  height: 310px;
  left: 350px;
  top: 291px;

  background: #d9d9d9;
  border-radius: 49px;
}
.editora label {
  position: absolute;
  width: 120px;
  height: 44px;
  left: 400px;
  top: 30px;

  font-family: "Montserrat";
  font-style: normal;
  font-weight: 900;
  font-size: 30px;
  line-height: 44px;

  text-align: center;

  color: #6c3a3a;
}
.editora ul {
  position: absolute;
  width: 117px;
  height: 29px;
  left: 0px;
  top: 80px;

  font-family: "Montserrat";
  font-style: normal;
  font-weight: 400;
  line-height: 29px;
  text-align: left;
  list-style-type: none;

  color: #6c3a3a;
}
.pesq {
  position: absolute;
  width: 180px;
  height: 30px;
  left: 400px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.pesq2 {
  position: absolute;
  width: 180px;
  height: 30px;
  left: 600px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.pesq3 {
  position: absolute;
  width: 180px;
  height: 30px;
  left: 800px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.pesq4 {
  position: absolute;
  width: 180px;
  height: 30px;
  left: 1000px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
input::placeholder {
  padding: 24px;
  color: #d9d9d9;
}
input {
  text-decoration-style: none;
  border: none;
}
input:focus {
  outline: none;
}
.btncad {
  position: absolute;
  width: 50px;
  left: 1200px;
  top: 373px;
  font-style: normal;
  padding: 5px;
  list-style: none;
  border: 2px solid #6c3a3a;
  list-style-type: none;
  outline: none;
  font-family: "Montserrat";
  cursor: pointer;
  border-radius: 24px;
  background-color: #ffffff;
  color: #6c3a3a;
}
.btncad:hover {
  background-image: linear-gradient(#6c3a3a, #5b3a3a);
  color: #ffffff;
}
button {
  position: absolute;
  width: 80px;
  height: 30px;
  left: 380px;
  top: 240px;

  font-family: "Montserrat";
  text-align: center;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
table {
  position: absolute;
  top: 425px;
  left: 368px;
}
table {
  width: 46%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid #3b2020;
  font-size: 1.1rem;
  text-align: center;
  color: #300707;
}
table thead {
  background-color: #3b2020;
  color: #ffffff;
}
table thead th {
  font-weight: bolder;
}
table tbody tr:nth-child(odd) {
  background-color: #6c3a3a;
}
</style>

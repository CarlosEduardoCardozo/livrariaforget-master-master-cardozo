<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      Id: "",
      Senha: "",
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
          Senha: this.Senha,
          Email: this.Email,
          Site: this.Site,
          SenhaUsuario: this.Senha,
        });
        this.Id = "";
        this.Senha = "";
        this.Email = "";
        this.Nome = "";
        this.Senha = "";
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
  <div class="livro">
    <label for="">Usuário</label>
  </div>
  <router-link to="/cadastro">
    <button>←VOLTAR</button>
  </router-link>
  <div class="cadastro">
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
      placeholder="Username"
      v-model="Nome"
      @keyup.enter="salvar"
    />
    <input
      class="pesq3"
      type="text"
      placeholder="Email"
      v-model="Site"
      @keyup.enter="salvar"
    />
    <input
      class="pesq4"
      type="text"
      placeholder="Nome"
      v-model="Senha"
      @keyup.enter="salvar"
    />
    <input
      class="pesq5"
      type="text"
      placeholder="Senha"
      v-model="SenhaUsuario"
      @keyup.enter="salvar"
    />
    <button @click="salvar" class="btncad">OK</button>
  </div>
  <table>
    <thead>
      <tr>
        <td>Id</td>
        <td>Nome</td>
        <td>Site</td>
        <td>Senha</td>
        <td>Nome</td>
      </tr>
    </thead>
    <tbody>
      <tr v-for="editora in editoras" :key="editora.id">
        <td>{{ editora.Id }}</td>
        <td>{{ editora.Nome }}</td>
        <td>{{ editora.Site }}</td>
        <td>{{ editora.Senha }}</td>
        <td>{{ editora.NomeUsuario }}</td>

        <td>
          <button class="btnedit" @click="alerta(editora)">Editar</button>
          <button class="btnexcluir" @click="excluir(editora)">Excluir</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>
<style scoped>
.livro {
  position: absolute;
  width: 970px;
  height: 350px;
  left: 350px;
  top: 291px;

  background: #d9d9d9;
  border-radius: 49px;
}
.livro label {
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
.livro ul {
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
  width: 110px;
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
  width: 160px;
  height: 30px;
  left: 520px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.pesq3 {
  position: absolute;
  width: 190px;
  height: 30px;
  left: 690px;
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
  left: 890px;
  top: 370px;

  font-family: "Montserrat";
  text-align: left;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.pesq5 {
  position: absolute;
  width: 130px;
  height: 30px;
  left: 1080px;
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
  left: 1230px;
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

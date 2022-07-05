<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_livro: "",
      novo_autor: "",
      nova_categoria: "",
      nova_editora: "",
      livros: [],
    };
  },
  methods: {
    salvar() {
      if (this.novo_livro !== "") {
        const novo_id = uuid();
        this.livros.push({
          id: novo_id,
          nome_livro: this.novo_livro,
          autor: this.novo_autor,
          categoria: this.nova_categoria,
          editora: this.nova_editora,
        });
        this.novo_livro = "";
        this.novo_autor = "";
        this.nova_categoria = "";
        this.nova_editora = "";
      }
    },
    excluir(livro) {
      const indice = this.livros.indexOf(livro);
      this.livros.splice(indice, 1);
    },
    alerta() {
      alert("Ok!");
    },
  },
};
</script>
<template>
  <main>
    <div class="livro">
      <label for="">Livro</label>
      <router-link to="/cadastro">
        <button>←VOLTAR</button>
      </router-link>
      <table>
        <thead>
          <tr>
            <td>Título</td>
            <td>Categoria</td>
            <td>Editora</td>
            <td>Autor</td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="livro in livros" :key="livro.id">
            <td>{{ livro.nome_livro }}</td>
            <td>{{ livro.categoria }}</td>
            <td>{{ livro.editora }}</td>
            <td>{{ livro.autor }}</td>

            <td>
              <button class="btnedit" @click="alerta(livro)">Editar</button>
              <button class="btnexcluir" @click="excluir(livro)">
                Excluir
              </button>
            </td>
          </tr>
        </tbody>
      </table>
      <div class="cadastro">
        <input
          class="pesq"
          type="text"
          placeholder="Título"
          v-model="novo_livro"
          @keyup.enter="salvar"
        />
        <input
          class="pesq2"
          type="text"
          placeholder="Categoria"
          v-model="nova_categoria"
          @keyup.enter="salvar"
        />
        <input
          class="pesq3"
          type="text"
          placeholder="Editora"
          v-model="nova_editora"
          @keyup.enter="salvar"
        />
        <input
          class="pesq4"
          type="text"
          placeholder="Autor"
          v-model="novo_autor"
          @keyup.enter="salvar"
        />
        <button @click="salvar" class="btncad">OK</button>
      </div>
    </div>
  </main>
</template>
<style scoped>
.livro {
  position: absolute;
  width: 920px;
  height: 310px;
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
table {
  position: absolute;
  top: 136px;
  left: 68px;
}
table {
  width: 85%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid #3b2020;
  font-size: 1.1rem;
  text-align: center;
  font-family: "Montserrat";
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
.cadastro {
  position: absolute;
  top: -280px;
  left: -349px;
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
  left: 310px;
  top: 240px;

  font-family: "Montserrat";
  text-align: center;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.btnexcluir {
  position: absolute;
  width: 80px;
  height: 30px;
  left: 327px;
  top: 103px;

  font-family: "Montserrat";
  text-align: center;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
.btnedit {
  position: absolute;
  width: 80px;
  height: 30px;
  left: 413px;
  top: 101px;

  font-family: "Montserrat";
  text-align: center;
  border-radius: 24px;
  background-color: #6c3a3a;
  color: #ffffff;
}
</style>

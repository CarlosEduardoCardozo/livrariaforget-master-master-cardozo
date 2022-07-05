<template>
  <main>
    <h3>Bem vindo a área de Administração</h3>
    <div class="txtabert">
      <p>Sistema desenvolvido por Carlos Cardozo e Eron Tiago</p>
      <a href="https://www.instagram.com/_cardozzoo_/"><p>@_cardozzoo_</p></a>
      <p>@eron.tiago</p>
      <p>Para acessar o painel de Administração clique no botão abaixo</p>
      <router-link to="/cadastro">
        <button>Acessar</button>
      </router-link>
    </div>
  </main>
</template>
<style scoped>
main {
  background-color: #6c3a3a;
  position: absolute;
  width: 265px;
  height: 950px;
  left: 0px;
  top: 0px;
}

h3 {
  position: absolute;
  width: 509px;
  height: 59px;
  left: 600px;
  top: 180px;

  font-family: "Montserrat";
  font-style: normal;
  font-weight: 900;
  font-size: 35px;
  line-height: 59px;

  text-align: center;

  color: #6c3a3a;
}
.txtabert {
  position: absolute;
  width: 380px;
  height: 59px;
  left: 675px;
  top: 350px;

  font-family: "Montserrat";
  text-align: center;
  text-decoration: none;
  list-style-type: none;

  color: #6c3a3a;
}
.txtabert button {
  position: absolute;
  width: 380px;
  height: 59px;
  left: 5px;
  top: 190px;

  font-family: "Montserrat";
  text-align: center;
  border-radius: 20px;
  background-color: #6c3a3a;
  color: #ffffff;
  cursor: pointer;
}
</style>

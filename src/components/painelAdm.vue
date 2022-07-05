<template>
  <main>
    <div class="painel">
      <router-link to="/">
        <span>Painel de Administração</span>
      </router-link>
      <img src="public\livrosbemvindo.png" class="imglivro" />
    </div>
  </main>
</template>
<style scoped>
main {
  background-color: #6c3a3a;
  position: absolute;
  width: 265px;
  height: 965px;
  left: 0px;
  top: 0px;
}

.painel {
  background: #d9d9d9;
  border-radius: 32px;
  position: absolute;
  width: 1250px;
  height: 131px;
  left: 167px;
  top: 53px;
}
.painel span {
  position: absolute;
  width: 780px;
  height: 59px;
  left: 40px;
  top: 35px;

  font-family: "Montserrat";
  font-style: normal;
  font-weight: 900;
  font-size: 35px;
  line-height: 59px;

  text-align: left;

  color: #6c3a3a;
}
.imglivro {
  position: absolute;
  right: 24px;
  top: 15px;
  width: 150px;
}
</style>

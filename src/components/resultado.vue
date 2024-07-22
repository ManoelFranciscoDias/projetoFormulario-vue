<script setup>

</script>
<template>
    <div v-if="mostrarResultado" class="resultado">
      <h1 style="color: white">RESULTADO</h1>
      <p>Nome: {{ dados.nome }}</p>
      <p>Email: {{ dados.email }}</p>
      <p>Senha: {{ dados.senha }}</p>
      <p>Confirme sua senha: {{ dados.confirmSenha }}</p>
      <p>Data: {{ dados.data }}</p>
      <p>Cidade: {{ dados.cidade }}</p>
      <p>Estado: {{ dados.estado }}</p>
      <p>Hobbies: {{ dados.hobbies }}</p>
      <p>Linguagem Favorita: {{ dados.linguagem }}</p>
      <p>
        Biografia: <br />
        "{{ dados.biografia }}"
      </p>

      <button @click="mostrarResultado = !mostrarResultado">VOLTAR</button>
    </div>
</template>

<style scoped>

.resultado {
  background-color: rgb(26, 24, 24);
  color: white;
  border-radius: 10px;
  padding: 40px;
  width: 40%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 7rem;
}

button {
  background-color: #2a5239;
  border: none;
  height: 40px;
  width: 30vh;
  color: white;
  border-radius: 10px;
  margin-top: 20px;
}

button:hover {
  background-color: #2d6d45;
}

p {
    color: white;
  text-align: center;
}

</style>
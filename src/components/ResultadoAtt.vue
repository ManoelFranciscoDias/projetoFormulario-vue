<script setup>
defineProps({
  nome: String,
  email: String,
  senha: String,
  confirm: String,
  data: Date,
  cidade: String,
  estado: String,
  hobbies: Array,
  linguagem: Array, 
  biografia: String
})

</script>
<template>
    <div class="resultado">
      <h1 style="color: white">RESULTADO</h1>
      <p>Nome: {{ nome }}</p>
      <p>Email: {{ email }}</p>
      <p>Senha: {{ senha }}</p>
      <p>Confirme sua senha: {{ confirm }}</p>
      <p>Data: {{ data }}</p>
      <p>Cidade: {{ cidade }}</p>
      <p>Estado: {{ estado }}</p>
      <p>Hobbies: {{ hobbies }}</p>
      <p>Linguagem Favorita: {{ linguagem }}</p>
      <p>
        Biografia: <br />
        "{{ biografia }}"
      </p>

      <button @click="$emit('voltar')">VOLTAR</button>
    </div>
</template>

<style scoped>


  .resultado {
  background-color: rgb(26, 24, 24);
  color: white;
  border-radius: 10px;
  padding: 40px;
  width: 40%;
  margin: 0 auto; 
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh; 
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
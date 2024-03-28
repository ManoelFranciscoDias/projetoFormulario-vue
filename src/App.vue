<script setup>
import { reactive, ref } from 'vue'

const mostrarResultado = ref(false)

const dados = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmSenha: '',
  data: Number,
  cidade: '',
})


</script>

<template>
  <div class="container">
    <div class="formulario">
      <h1>FORMULARIO</h1>

      <div class="row">
        <input type="text" v-model="dados.nome" placeholder="Nome" />
      </div>
      <div class="row">
        <input type="text" v-model="dados.email" placeholder="Email" />
      </div>
      <div class="row">
        <input type="text" v-model="dados.senha" placeholder="Senha" />
      </div>
      <div class="row">
        <input type="text" v-model="dados.confirmSenha" placeholder="Confirme sua senha" />
      </div>
      <div class="row">
        <input type="date" v-model="dados.data" />
      </div>
      <div class="row">
        <input type="text" v-model="dados.cidade" />
      </div>

      <button @click="mostrarResultado = !mostrarResultado">Mostrar</button>
    </div>
    <div class="resultado">
      <h1>RESULTADO</h1>
      <p>Nome: {{ dados.nome }}</p>
      <p>Email: {{ dados.email }}</p>
      <p>Senha: {{ dados.senha }}</p>
      <p>Confirme sua senha: {{ dados.confirmSenha }}</p>
      <p>Data: {{ dados.data }}</p>
      <p>Cidade: {{ dados.cidade }}</p>

      <p>{{ mostrarResultado }}</p>
    </div>
  </div>
</template>

<style scoped>
.formulario {
  background-color: aqua;
}

.resultado {
  background-color: blue;
}

.container {
  display: flex;
  gap: 2rem;
  justify-content: center;
  margin-top: 1rem;
}

.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 10px;
  padding: 20px;
}

h1 {
  text-align: center;
}

.formulario, .row {
width: 80%;
margin: 1.3 0;
display: flex;
flex-direction: column;
}
</style>

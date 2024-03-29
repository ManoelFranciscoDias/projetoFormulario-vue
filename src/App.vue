<script setup>
import { reactive, ref } from 'vue'

const mostrarResultado = ref(false)

const dados = reactive({
  nome: '',
  sobrenome: '',
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


    <h1 style="color: white;">FORMULARIO</h1>  

      <div class="row">
        <label for="">Nome:</label>
        <input type="text" v-model="dados.nome"/>
      
        <label for="">Sobrenome:</label>
        <input type="text" v-model="dados.sobrenome"/>
      </div>
      <div class="row">
      <label for="">Email:</label>
        <input type="text" v-model="dados.email"/>
      </div>
      <div class="row">
        <label for="">Senha:</label>
        <input type="text" v-model="dados.senha"/>
      </div>
      <div class="row">
        <label for="">Confirme a senha:</label>
        <input type="text" v-model="dados.confirmSenha"/>
      </div>
      <div class="row">
        <label for="">Data de nascimento:</label>
        <input type="date" v-model="dados.data" />
      </div>
      <div class="row">
        <label for="">Cidade:</label>
        <input type="text" v-model="dados.cidade" />
      </div>

      <button @click="mostrarResultado = !mostrarResultado">MOSTRAR</button>
    </div>
    <div class="resultado">
      <h1 style="color: white;">RESULTADO</h1>
      <p>Nome: {{ dados.nome }}</p>
      <p>Sobrenome: {{ dados.sobrenome }}</p>
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
  background-color: rgb(26, 24, 24);
  
}

.resultado {
  background-color: rgb(26, 24, 24);
  color: white
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
  min-height: 20vh;
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
align-items: center;

}




button {
  background-color:#2a5239;
  border: none;
  height: 30px;
  width: 40vh;
  color: white;
  border-radius: 10px;
  margin-top: 20px;
}

button:hover {
  background-color:#2d6d45;
  
}


</style>

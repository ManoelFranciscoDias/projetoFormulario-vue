<script setup>
import { reactive } from 'vue'

const emit = defineEmits(['resultado', 'dados'])

const dados = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmSenha: '',
  data: '',
  cidade: '',
  estado: '',
  hobbies: [],
  linguagem: [],
  biografia: ''
})

const estados = [
  { uf: 'AC', name: 'Acre' },
  { uf: 'AL', name: 'Alagoas' },
  { uf: 'AP', name: 'Amapá' },
  { uf: 'AM', name: 'Amazonas' },
  { uf: 'BA', name: 'Bahia' },
  { uf: 'CE', name: 'Ceará' },
  { uf: 'DF', name: 'Distrito Federal' },
  { uf: 'ES', name: 'Espírito Santo' },
  { uf: 'GO', name: 'Goiás' },
  { uf: 'MA', name: 'Maranhão' },
  { uf: 'MT', name: 'Mato Grosso' },
  { uf: 'MS', name: 'Mato Grosso do Sul' },
  { uf: 'MG', name: 'Minas Gerais' },
  { uf: 'PA', name: 'Pará' },
  { uf: 'PB', name: 'Paraíba' },
  { uf: 'PR', name: 'Paraná' },
  { uf: 'PE', name: 'Pernambuco' },
  { uf: 'PI', name: 'Piauí' },
  { uf: 'RJ', name: 'Rio de Janeiro' },
  { uf: 'RN', name: 'Rio Grande do Norte' },
  { uf: 'RS', name: 'Rio Grande do Sul' },
  { uf: 'RO', name: 'Rondônia' },
  { uf: 'RR', name: 'Roraima' },
  { uf: 'SC', name: 'Santa Catarina' },
  { uf: 'SP', name: 'São Paulo' },
  { uf: 'SE', name: 'Sergipe' },
  { uf: 'TO', name: 'Tocantins' }
]

function validacaosenha() {
  if (dados.senha !== dados.confirmSenha || dados.confirmSenha !== dados.senha) {
    
    alert('As senhas não são iguais')
    
  } else if (
    dados.nome == '' ||
    dados.email == '' ||
    dados.senha == '' ||
    dados.confirmSenha == '' ||
    dados.cidade == '' ||
    dados.estado == '' ||
    dados.hobbies == '' ||
    dados.linguagem == '' ||
    dados.data == ''
  ) {

    alert(`Existem campos vazios!`)
    
  }
   
  else {
    emit('dados', {
      nome: dados.nome,
      email: dados.email,
      senha: dados.senha,
      confirmSenha: dados.confirmSenha,
      data: dados.data,
      cidade: dados.cidade,
      estado: dados.estado,
      hobbies: dados.hobbies,
      linguagem: dados.linguagem,
      biografia: dados.biografia
    })
  }
}
</script>

<template>
  <div class="container">
    <div v-if="!mostrarResultado" class="formulario">
      <h1 style="color: white">FORMULARIO</h1>

      <div class="column">
        <label for="">Nome:</label>
        <input type="text" v-model="dados.nome" />
      </div>
      <div class="column">
        <label for="">Email:</label>
        <input type="email" v-model="dados.email" />
      </div>
      <div class="column">
        <label for="senha">Senha:</label>
        <input type="password" v-model="dados.senha" />
      </div>
      <div class="column">
        <label for="ConfirmeSenha">Confirme a senha:</label>
        <input type="password" v-model="dados.confirmSenha" />
      </div>
      <div class="column">
        <label for="">Data de nascimento:</label>
        <input type="date" v-model="dados.data" />
      </div>
      <div class="column">
        <label for="">Cidade:</label>
        <input type="text" v-model="dados.cidade" />
      </div>
      <div class="column">
        <label for="stateField" class="form-label">Estado:</label>
        <select class="form-select" id="stateField" v-model="dados.estado">
          <option selected disabled value="">Selecionar...</option>
          <option v-for="estado of estados" :key="estado.uf" :value="estado.name">
            {{ estado.name }}
          </option>
        </select>
      </div>
      <div>
        <p>Hobbies:</p>
        <div class="row">
          <div class="check-item">
            <input
              class="hobbie01"
              type="checkbox"
              id="hobbies01"
              value="Esportes"
              v-model="dados.hobbies"
            />
            <label for="hobbies01">Esportes</label>
          </div>
          <div class="check-item">
            <input
              class="hobbies02"
              type="checkbox"
              id="hobbies02"
              value="Cozinhar"
              v-model="dados.hobbies"
            />
            <label for="hobbies02">Cozinhar</label>
          </div>
          <div class="check-item">
            <input
              class="hobbies03"
              type="checkbox"
              id="hobbies03"
              value="Jogos"
              v-model="dados.hobbies"
            />
            <label for="hobbies03">Jogos</label>
          </div>
          <div class="check-item">
            <input
              class="hobbies04"
              type="checkbox"
              id="hobbies04"
              value="Filmes"
              v-model="dados.hobbies"
            />
            <label for="hobbies04">Filmes</label>
          </div>
        </div>

        <p style="margin-top: 20px">Linguagem Favorita:</p>
      </div>

      <div class="row">
        <div class="check-item">
          <input class="radio" type="radio" v-model="dados.linguagem" value="C" id="linguagemC" />
          <label for="linguagemC">Python</label>
        </div>
        <div class="check-item">
          <input
            class="radio"
            type="radio"
            v-model="dados.linguagem"
            value="Python"
            id="linguagemPython"
          />
          <label for="linguagemPython">C</label>
        </div>
        <div class="check-item">
          <input
            class="radio"
            type="radio"
            v-model="dados.linguagem"
            value="Java"
            id="lingaugemJava"
          />
          <label for="linguagemJava">Java</label>
        </div>
      </div>

      <div style="margin-top: 15px" class="column">
        <label for="">Biografia:</label>
        <textarea
          v-model="dados.biografia"
          name="biografia"
          id="biografia"
          cols="50"
          rows="15"
          required
        ></textarea>
      </div>

      <button @click="validacaosenha">ENVIAR</button>
    </div>
  </div>
</template>
<style scoped>
.formulario {
  background-color: rgb(24, 26, 25);
  border-radius: 10px;
  padding: 40px;
  width: 40%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.container {
  display: flex;
  gap: 2rem;
  justify-content: center;
  margin-top: 2rem;
}

.column {
  width: 40%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.check-item {
  display: flex;
  flex-direction: row;
}

.row {
  display: flex;
  flex-direction: row;
  gap: 1rem;
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

textarea {
  background-color: rgb(41, 41, 41);
  color: white;
  border: none;
  border-radius: 10px;
  padding: 15px;
}

textarea:hover {
  background-color: rgb(27, 24, 24);
  color: white;
  border: none;
}

input[type='checkbox'] {
  width: 20px;
  margin-right: 0.2rem;
  margin-top: 0.3rem;
}

input[type='radio'] {
  width: 50px;
  margin-right: 0.2rem;
  margin-top: 0.3rem;
}

.hobbie {
  color: white;
  text-align: center;
}

p {
  color: white;
  text-align: center;
}
</style>
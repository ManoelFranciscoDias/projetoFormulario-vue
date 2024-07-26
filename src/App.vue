<script setup>
import { ref } from 'vue'
import ResultadoAtt from '@/components/ResultadoAtt.vue'
import FormularioAtt from '@/components/FormularioAtt.vue'
const mostrarResultado = ref(true)
const nome = ref(null)
const email = ref(null)
const senha = ref(null)
const confirmSenha = ref(null)
const data = ref(null)
const cidade = ref(null)
const estado = ref(null)
const hobbies = ref(null)
const linguagem = ref(null)
const biografia = ref(null)

function passardados(dados) {
  nome.value = dados.nome
  email.value = dados.email
  senha.value = dados.senha
  confirmSenha.value = dados.confirmSenha
  data.value = dados.data
  cidade.value = dados.cidade
  estado.value = dados.estado
  hobbies.value = dados.hobbies
  linguagem.value = dados.linguagem
  biografia.value = dados.biografia

  mostrarResultado.value = !mostrarResultado.value
}
</script>

<template>
  <FormularioAtt @dados="passardados" v-if="mostrarResultado"></FormularioAtt>
  <ResultadoAtt
    :nome="nome"
    :email="email"
    :senha="senha"
    :confirm="confirmSenha"
    :data="data"
    :cidade="cidade"
    :estado="estado"
    :hobbies="hobbies"
    :linguagem="linguagem"
    :biografia="biografia"

    @voltar="mostrarResultado = !mostrarResultado"
    v-else
  ></ResultadoAtt>
</template>

<style scoped></style>

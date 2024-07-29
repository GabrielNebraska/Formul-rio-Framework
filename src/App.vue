<script setup>
import { reactive } from 'vue'
import FormsResultado from './components/FormsResultado.vue'
import FormsOriginal from './components/FormsOriginal.vue'

const usuario = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmarsenha: '',
  datadenascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobby: [],
  linguagens: '',
  biografia: ''
})

function salvar(novoResultado) {
  Object.assign(usuario, novoResultado)
}
</script>

<template>
  <FormsOriginal @resultado="salvar" />
  <FormsResultado :usuario="usuario" />
</template>

<style scoped></style>
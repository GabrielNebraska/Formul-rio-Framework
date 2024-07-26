<script setup>

import { reactive } from 'vue';
import FormsOriginal  from './components/FormsOriginal.vue'
import FormsResultado from './components/FormsResultado.vue'

const usuario = reactive({
file: '',
name: '',
email: '',
password: '',
confirmpassword: '',
city: '',
state: '',
preferredLinguages: [],
bibliography: '',
sexo: ''
})

const objetoTeste = reactive({})


function salvar(novoResultado) {
  objetoTeste.value = novoResultado
}

</script>

<template>

<FormsOriginal @resultado="salvar" />
<FormsResultado :usuario="objetoTeste" />

</template>
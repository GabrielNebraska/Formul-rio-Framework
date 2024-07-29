<script setup>
defineProps(['usuario'])
</script>
<template>
  <div class="resultado">
    <h1>Resultado</h1>

    <div style="width: 18rem;"  >      
      <img v-if="usuario.avatar" class="card-img-top" :src="usuario.avatar" />
      </div>
    <p>Nome: {{ usuario.nome }}</p>
    <p>Email: {{ usuario.email }}</p>
    <p>Senha: {{ usuario.senha }}</p>
    <p>Data de Nascimento: {{ usuario.datadenascimento }}</p>
    <P> Endereço: {{ usuario.endereco }} </P>
    <P> Cidade: {{ usuario.cidade }} </P>
    <p>Estado: {{ usuario.estado }}</p>
    <p>Biografia: {{ usuario.biografia }}</p>
    <p>Linguagem: {{ usuario.linguagens }}</p>
    <p>Hobbies: {{ usuario.hobby }}</p>
    <p>Sexo: {{ usuario.sexo }}</p>
  </div>
</template>
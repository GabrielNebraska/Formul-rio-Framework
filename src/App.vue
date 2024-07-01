<script setup>

import { ref } from 'vue';

const user = ref({

name: '',
email: '',
password: '',
confirmpassord: '',
city: '',
state: '',
preferredLinguages: '',
bibliography: ''

})
 
const states = [
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
</script>

<template>
  
<div class="container">
  <main>

<div>
  <label for="nameFild" class="form-label">Name</label> <br> 
  <input type="Name" v-model="user.name" size="25" minlength="10" maxlength="40">
</div>
<div>
  <label>Email</label> <br>
  <input type="Email" v-model="user.email" size="25" minlength="10" maxlength="40">
</div> 
<div>
  <label>Password</label> <br>
  <input type="password" v-model="user.password" size="25" minlength="6" maxlength="20">
</div> 
<div>
  <label>Confirm Passord</label> <br>
  <input type="ConfirmPassord" v-model="confirmpassord" size="25" minlength="6" maxlength="20">
</div>


  <select v-model="sexo"> 
  <option value="Masc">Masculine</option>
  <option value="Fem">Feminine</option>
  <option value="Other">Other</option>
  </select>

  
  <div>
  <label>City</label> <br>
  <input type="City" v-model="user.city" size="25" minlength="10" maxlength="40">
  </div>


  <div>
  <label>State</label> <br>
  <select v-model="state">
  <option selected disabled value="">Selecionar...</option>
  <option v-for="state of states" :key="state.uf" :value="state.uf">
  {{ state.name }}
  </option>
  </select>
  </div>

  <div>

    <label>Your Preferred Linguage</label> <br> 
    <input type="text" v-model="preferredLinguages" size="25" minlength="2" maxlength="30"> 

  </div>
  <div>
    <label>Bibliography</label> <br>
  <textarea type="text" v-model="user.bibliography" cols="50" rows="6"> </textarea> 
</div>




</main>

</div>

</template>

<style scoped>
</style>


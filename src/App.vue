<script setup>

import { ref } from 'vue';

const user = ref({

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

function handleFileUpload(e) {
  const target = e.target
  console.log(target)
  if (target && target.files) {
    const file = target.files[0]
    user.value.avatar = URL.createObjectURL(file)
  }
}

const mostrarPerfil = ref(false)

</script>

<template>
  
<div class="container">
  <main>

    <selection v-if="mostrarPerfil" name="form" mode="out-in">

      <div class="card" style="width: 18rem;"  >      
        <img v-if="user.avatar" class="card-img-top" :src="user.avatar" />
        </div>
        <div class="card-body">
          <h5 class="card-title">{{user.name}}</h5>
        </div>
        <div>
        <ul list-group list-group-flush>
          <li class="group-list-item">{{user.email}}</li>
          <li class="group-list-item">{{user.city}}</li>
          <li class="group-list-item">{{user.state}}</li>
          <li class="group-list-item">{{user.preferredLinguages}}</li>
          <li class="group-list-item">{{user.bibliography}}</li>
          <li class="group-list-item">{{user.sexo}}</li>
        </ul>
        <button class="btn btn-info" @click="mostrarPerfil = false">Esconder</button>
        </div>

      
    </selection>

<div class="input-group mb-3">
  <label for="inputGroupFile01" class="input-group-text">Avatar</label> 
  <input class="form-control" type="file" id="inputGroupFile01" @change="handleFileUpload($event)">
</div>

<div class="form-floating mb-3">
  <input type="name" v-model="user.name" class="form-control" id="floatingInput" placeholder="name" minlength="6" maxlength="45" required>
  <label for="floatingInput">Name</label>
</div>

<div class="form-floating mb-3">        
  <input type="email" v-model="user.email" class="form-control" id="floatingInput" placeholder="name@example.com" minlength="6" maxlength="40" required>
  <label for="floatingInput">Email address</label>
</div>

<div class="form-floating mb-3">
  <input type="password" v-model="user.password" class="form-control" id="floatingInput" placeholder="password" minlength="6" maxlength="20" required>
  <label for="floatingInput">Password</label>
</div>

<div class="form-floating mb-3">
  <input type="password" v-model="user.confirmpassword" class="form-control" id="floatingInput" placeholder="Confirm password" minlength="6" maxlength="20" required>
  <label for="floatingInput">Confirm password</label>
</div>
  
  <div class="form-floating mb-3"> 
  <input type="text" v-model="user.city" class="form-control" id="floatingInput" placeholder="Your city" minlength="10" maxlength="40" required>
  <label for="floatingInput">City</label>  
</div>

<div class="form-floating mb-3">
    
    <textarea type="text" v-model="user.bibliography" class="form-control" id="floatingInput" placeholder="Bibliography" cols="50" rows="6" required> </textarea> 
    <label for="floatingInput">Bibliography</label> 
  </div>
  

<div>
<label>Your preferred Linguage</label> 
    <select v-model="user.preferredLinguages" class="form-select" size="3" aria-label="aaaaaaa" required>
      <option>C#</option>
      <option>JavaScript</option>
      <option>Java</option>
      <option>PHP</option>
      <option>Python</option>
      <option>Swift</option>
      <option>Go</option>
    </select>
  </div>

  <br>

  <div>
  <label>Sex</label> <br> 
  <select v-model="user.sexo"> 
  <option value="Masc">Masculine</option>
  <option value="Fem">Feminine</option>
  <option value="Other">Other</option>
  </select>
  </div>

  <br>

  <div>
  <label for="stateField" class="form-label">State</label> <br>
  <select class="form-select" v-model="user.state" id="statefield">
  <option selected disabled value="">Selecionar...</option>
  <option v-for="state of states" :key="state.uf" :value="state.uf">
  {{ state.name }}
  </option>
  </select>
  </div>

  <button class="btn btn-primary" type="submit" @click="mostrarPerfil = true">Enviar</button>

</main>

</div>

</template>

<style scoped>
</style>


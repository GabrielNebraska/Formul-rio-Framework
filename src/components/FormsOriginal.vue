

<script setup>

import { ref } from 'vue';

const emit = defineEmits(['resultado'])

const usuario = ({...emit.resultado})
 
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

  <main class="container">

<div class="input-group mb-3">
  <label for="inputGroupFile01" class="input-group-text">Avatar</label> 
  <input class="form-control" type="file" id="inputGroupFile01" @change="handleFileUpload($event)">
</div>

<div class="form-floating mb-3">
  <input type="name" v-model="usuario.name" class="form-control" id="floatingInput" placeholder="name" minlength="3" maxlength="45" required>
  <label for="floatingInput">Name</label>
</div>

<div class="form-floating mb-3">        
  <input type="email" v-model="usuario.email" class="form-control" id="floatingInput" placeholder="name@example.com" minlength="6" maxlength="40" required>
  <label for="floatingInput">Email address</label>
</div>

<div class="form-floating mb-3">
  <input type="password" v-model="usuario.password" class="form-control" id="floatingInput" placeholder="password" minlength="6" maxlength="20" required>
  <label for="floatingInput">Password</label>
</div>

<div class="form-floating mb-3">
  <input type="password" v-model="usuario.confirmpassword" class="form-control" id="floatingInput" placeholder="Confirm password" minlength="6" maxlength="20" required>
  <label for="floatingInput">Confirm password</label>
</div>
  
  <div class="form-floating mb-3"> 
  <input type="text" v-model="usuario.city" class="form-control" id="floatingInput" placeholder="Your city" minlength="2" maxlength="40" required>
  <label for="floatingInput">City</label>  
</div>

<div class="form-floating mb-3">
    
    <textarea type="text" v-model="usuario.bibliography" class="form-control" id="floatingInput" placeholder="Bibliography" cols="50" rows="6" required> </textarea> 
    <label for="floatingInput">Bibliography</label> 
  </div>
  

<div>
<label>Your preferred Linguage</label> 
    <select v-model="usuario.preferredLinguages" class="form-select" size="3" aria-label="aaaaaaa" required>
      <option>C#</option>
      <option>JavaScript</option>
      <option>Java</option>
      <option>PHP</option>
      <option>Python</option>
      <option>Swift</option>
      <option>Go</option>
    </select>
  </div>


  <div>
  <label>Sex</label> 
  <select class="form-select" v-model="usuario.sexo"> 
  <option value="Masc">Masculine</option>
  <option value="Fem">Feminine</option>
  <option value="Other">Other</option>
  </select>
  </div>
  

  <div>
  <label for="stateField" class="form-label">State</label> 
  <select class="form-select" v-model="usuario.state" id="statefield">
  <option selected disabled value="">Selecionar...</option>
  <option v-for="state of states" :key="state.uf" :value="state.uf">
  {{ state.name }}
  </option>
  </select>
  </div>


  <button class="btn btn-primary" type="submit" @click="mostrarPerfil = true">Enviar</button>


  <button class="btn btn-info" @click="mostrarPerfil = false">Esconder</button>
</main>





</div>

</template>

<style scoped>
.title{
  align-items: center;
}
.corpo{

  filter: drop-shadow(2px 2px 6px rgb(0, 0, 0));
  width: 18rem;
  background-color:silver;
  border-radius: 3.5%;
}

.container{

  display:block;
  max-width: 600px;
    margin: 0 auto;
    padding: 20px;
background-color: antiquewhite;

}

</style>


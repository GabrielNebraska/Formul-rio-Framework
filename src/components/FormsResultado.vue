<script setup>

defineProps(['usuario'])

</script>


<template>
  
  
<div class="resultado">
    <div class="card" style="width: 18rem;"  >      
      <img v-if="usuario.avatar" class="card-img-top" :src="usuario.avatar" />
      </div>
      <div>
        <h5 class="title">{{usuario.name}}</h5>
      <ul list-group list-group-flush>
        <li class="group-list-item">{{usuario.email}}</li>
        <li class="group-list-item">{{usuario.city}}</li>
        <li class="group-list-item">{{usuario.state}}</li>
        <li class="group-list-item">{{usuario.preferredLinguages}}</li>
        <li class="group-list-item">{{usuario.bibliography}}</li>
        <li class="group-list-item">{{usuario.sexo}}</li>
      </ul>
    </div>
</div>
    
  

</template>

<style>

.title{
  align-items: center;
}
.resultado{

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
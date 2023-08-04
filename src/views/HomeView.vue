<template>
  <div id="HomeView">
  
    <ListaComponent titulo="Lista de Cursos"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ListaComponent from '@/components/ListaComponent.vue';

export default {
  name: 'HomeView',
  components: {
    ListaComponent
  }
}
</script>

<style scoped>
#HomeView{
  background-color:rgb(67, 226, 210);
}

#HomeView{
  margin-left: 0px;
  margin-right: 0px;
  animation-name: desplazamiento;
  animation-duration: 2s;
  animation-iteration-count: initial;
  animation-timing-function: linear;
}

@keyframes desplazamiento{
  0%{
    margin-right: 1200px;
    
  }
  50%{
    margin-right: 600px;
    background: rgb(75, 198, 236);    
  }
  75%{
    background: rgb(53, 177, 214);
  }
  100%{
    margin-right: 0px;
  }
}

</style>

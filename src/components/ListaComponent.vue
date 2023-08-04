<template>
  <div id="ListaComponent">
    <h1>{{ titulo }}</h1>
        <!-- <div class="tarjetas" v-for="curso in datos" v-bind:key="curso.id">  -->
        <div class="tarjetas" v-for="curso in consultarNoCompletados" v-bind:key="curso.id">
            <b-card
              v-bind:title="curso.nombre"
              v-bind:img-src="curso.img"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem;"
              class="mb-2"
            >
              <b-card-text>
                {{ curso.descripcion }}
              </b-card-text>

              <b-card-text>
                Completado: <strong> {{ curso.completado}} </strong>
              </b-card-text>

              <b-button href="#" variant="primary">Go somewhere</b-button>
            </b-card>
      </div>
      <div class="container">
        <div class="bubbles">
            <span style="--i:11;"></span>
            <span style="--i:12;"></span>
            <span style="--i:24;"></span>
            <span style="--i:10;"></span>
            <span style="--i:14;"></span>
            <span style="--i:23;"></span>
            <span style="--i:18;"></span>
            <span style="--i:16;"></span>
            <span style="--i:19;"></span>
            <span style="--i:20;"></span>
            <span style="--i:22;"></span>
            <span style="--i:25;"></span>
            <span style="--i:18;"></span>
            <span style="--i:21;"></span>
            <span style="--i:15;"></span>
            <span style="--i:13;"></span>
            <span style="--i:26;"></span>
            <span style="--i:17;"></span>
            <span style="--i:13;"></span>
            <span style="--i:28;"></span>
        </div>
        </div>
    

  </div>
</template>

<script>
import { mapState,mapActions, mapGetters } from 'vuex';
export default {
  name: 'ListaComponent',
  props: {
    titulo: String
  },
  data:function(){
    return{

    }
  },
  methods:{
    ...mapActions('datos_cursos',['consultarCursos']),
  },
  computed:{
    ...mapState('datos_cursos',['datos']),
    ...mapGetters('datos_cursos',['consultarNoCompletados']),
  },
  watch:{},
  created(){
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#ListaComponent{
  margin: 2%;
}

.tarjetas{
  display: inline-block;
  margin: 2%;
  transition: all 300ms;
}

.tarjetas:hover{
  background: rgb(200, 16, 123);
  font-size: 19px;
  padding: 5px;
  border-radius: 10px;
}

*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  min-height: 100vh;
  background: #0c192c;
}

.container{
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.bubbles{
  position: relative;
  display: flex;
}

.bubbles span{
  position: relative;
  width: 30px;
  height: 30px;
  background: #4fc3dc;
  margin: 0 4px;
  border-radius: 50%;
  box-shadow: 0 0 0 10px #4fc3dc44,
  0 0 50px #4fc3dc,
  0 0 100px #4fc3dc;
  animation: animate 15s linear infinite;
  animation-duration: calc(125s / var(--i));
}

.bubbles span:nth-child(even)
{
  box-shadow: 0 0 0 10px #ff2d7544,
  0 0 50px #ff2d75,
  0 0 100px #ff2d75;
}

@keyframes animate {
  0%{
    transform: translateY(100vh) scale(0);
  }
  100%{
    transform: translateY(-10vh) scale(1);
  }
}


</style>

<template>
  <div id="app">
    <h2>{{titulo}}</h2>
    <hr>
    <div class="container">
      <div class="form">
          <div class="form-group">
              <label for="">Nombre</label>
              <input type="text" class="form-control" v-model="registro.nombre">
              
          </div>

          <div class="form-group">
              <label for="">Colegio</label>
              <input type="text" class="form-control" v-model="registro.colegio">
          </div>
          <hr>
          <div class="btn btn-primary" @click="agregarEstudiante()">
            Guardar
          </div>
          <hr>
          <div class="row">
            <div class="col-5" v-for="(registro,index) in registros" :key="registro[index]">
                  <div class="card">
                    <div class="form-group">
                      <h3>Nombre:</h3>
                      <p>{{ registro.nombre }} </p>
                      <hr>
                      <h3>Colegio:</h3>
                      <p>{{ registro.colegio }} </p>
                    </div>
                  </div>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      titulo: 'Bienvenido a la 1ra App Vue.js ramosDev',
      registro:{
        nombre:'',
        colegio:''
      },
      registros:[
        {
          nombre:'Juan Perez',
          colegio:"Juan Perez"
        }
      ]
    }
  },
  methods:{
    agregarEstudiante:function(){
      const{nombre,colegio}=this.registro;
      this.registros.push({nombre,colegio})
    } 
  }
};
</script>



<template>
  <div id="app">
    <div class="contenedor">
      <h1>Crear nueva tarea</h1>
      <label>
        Ingresar nueva tarea
        <input type="text" v-model="tarea" />
      </label>
      <button @click="addTarea" type="button" class="btn btn-success btn-sm">
        Agregar
      </button>
      <ul v-for="(tarea, index) in tareas" :key="index" Class="list-group">
        <li class="list-group-item">{{ index + 1 }} - {{ tarea }}</li>
      </ul>
      
    </div>
  </div>
</template>

<script>



export default {
  name: "App",
  data() {
    return {
      tarea: "",
      tareas: [],
    };
  },
  methods: {
    addTarea() {
      const { tarea } = this;
      this.tareas.push(tarea);
      this.tarea = "";
    },
  },
};
</script>

<style>
.btn {
  margin-left: 1rem;
  margin-bottom: 0.3rem;
}

.contenedor {
  text-align: center;
}

.list-group-item {
  align-self: center;
  width: 40%;
}
</style>

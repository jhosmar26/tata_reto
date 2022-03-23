<template>
  <div class="h-screen flex">
    <section class="flex w-full bg-gradient-to-tr from-blue-800 to-purple-700 justify-center py-10">
      <div class="bg-white pt-3.5 px-8 pb-8 rounded-xl w-full max-w-screen-lg">
        <div>
          <h1 class="text-gray-800 font-bold text-2xl uppercase">Lista de tareas</h1>
          <label>
            <span>Tarea:</span>
            <input :v-model="toAdd" class="border" type="text">
            {{toAdd}}
            <button type="submit" @click.prevent="()=>addTodo(toAdd)">send</button>
          </label>
          <ul>
            <li v-for="tarea, i in tareas" :key="i">
              <input type="checkbox" :value="i" v-model="checked">
              {{tarea}}
              <!-- <input v-if="" type="button" value="x"> -->
            </li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>


<script>
  export default {
    name: 'tareas',
    data() {
      return {
        toAdd: "",
        tareas: ["hacer la comida", "tareas"],
        checked:[]
      }
    },
    methods: {
      addTodo(value) {
        this.tareas.push(value)
      }
    }
  }
</script>
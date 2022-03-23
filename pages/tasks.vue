<template>
  <div class="h-screen flex">
    <section class="flex w-full bg-gradient-to-tr from-blue-800 to-purple-700 justify-center py-10">
      <div class="bg-white pt-3.5 px-8 pb-8 rounded-xl w-full max-w-screen-lg">
        <div>
          <h1 class="text-gray-800 font-bold text-2xl uppercase">Lista de tareas</h1>
          <!-- <label> -->
            <span>Tarea:</span>
            <input pattern="[a-zA-Z0-9]+" v-model="toAdd" class="border" type="text" />
            <button type="submit" @click.prevent="addTodo">send</button>
          <!-- </label> -->
          <ul>
            <li v-for="tarea, i in tasks" :key="i">
              <label class="flex items-center max-w-sm">
                <input type="checkbox" :value="i" v-model="checked">
                {{tarea}}
                <button class="relative inline-block w-5 h-5 bg-blue-500 hover:bg-blue-700 text-white rounded-full ml-auto" v-if="checked.indexOf(i) === -1" @click="() => deleteTask(i)">
                  <span class="block -mt-1 leading-none">x</span>
                </button>
              </label>
            </li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>


<script>
  export default {
    name: 'tasks',
    data() {
      return {
        toAdd: "",
        tasks: ["hacer la comida", "tasks"],
        checked:[]
      }
    },
    methods: {
      addTodo() {
        if(this.toAdd.match(/[a-zA-Z0-9]+/)){
          this.tasks.push(this.toAdd);
          this.toAdd = "";
        } else {
          alert("Solo se acepta valores alfanuméricos")
        }
      },
      deleteTask(taskIndex) {
        this.tasks.splice(taskIndex,1);
        // this.checked = this.checked.filter((e)=>{ return e !== taskIndex })
      }
    }
  }
</script>
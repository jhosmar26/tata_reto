<template>
  <div>
    <form class="bg-white pt-3.5 px-8 pb-8 rounded-xl" @submit.prevent="login">
      <h1 class="relative text-gray-800 font-bold text-2xl mb-2 -mb-3.5 bg-white w-max ml-2 px-2">Login</h1>
      <div class="flex flex-col md:flex-row md:gap-14 border px-5 py-8 items-center">
        <div class="flex flex-col gap-3">
          <label>
            <div class="select-none">Usuario</div>
            <div class="flex items-center border-2 py-2 px-3 rounded-2xl">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207" />
              </svg>
              <input id="" v-model="name" class="pl-2 outline-none border-none" type="text" name="" placeholder="test..." required />
            </div>
          </label>
          <label>
            <div class="select-none">Contraseña</div>
            <div class="flex items-center border-2 py-2 px-3 rounded-2xl">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-400" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z" clip-rule="evenodd" />
              </svg>
              <input id="" v-model="name" class="pl-2 outline-none border-none" type="text" name="" placeholder="..." required />
            </div>
          </label>
        </div>
        <button type="submit" class="block w-full bg-indigo-600 mt-4 px-4 py-2 rounded-2xl text-white font-semibold mb-2">Ingresar</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'LoginForm',
  data() {
    return {
      name: "test01",
      password: "test01",
      errorMessage: false,
      credentials: {name: "test01", password: "test01"}
    }
  },
  methods: {
    login() {
      if(this.validateCredentials()) {
        this.$router.push("/tareas")
      }
    },
    validateCredentials() {
      return this.name === this.credentials.name && this.password === this.credentials.password
    }
  }
}
</script>

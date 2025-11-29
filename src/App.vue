<template>
  <div class="h-screen w-full bg-[url('/img/cartas.jpg')] bg-cover bg-center flex flex-col justify-between">
    
  
    <div class="flex flex-1 items-center justify-center px-6 py-12">
      <div class="w-full max-w-md bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl p-8 shadow-xl">

        <h2 class="text-center text-2xl font-bold text-white">
          ¡Bienvenido! Decime tu nombre y empecemos a jugar
        </h2>

        <form class="space-y-6 mt-8">
          <div>
            <label for="nombre" class="block text-sm font-medium text-gray-100">
              Nombre
            </label>

            <input
              id="nombre"
              class="mt-2 block w-full rounded-md bg-white/70 px-3 py-1.5
                     text-base text-black placeholder:text-gray-600 
                     outline-none focus:ring-2 focus:ring-indigo-500"
            />
          </div>

          <button
            type="button"
            class="w-full rounded-md bg-indigo-500 px-3 py-2 text-sm font-semibold text-white hover:bg-indigo-400"
          >
            ¡Empecemos!
          </button>
        </form>

      </div>
    </div>

    <div class="w-full flex justify-center px-8 py-8">
      <div class="p-2 inline-flex items-center">
      <button class="bg-blue-700 text-white py-2 px-4 rounded-full hover:bg-blue-800 focus:outline-none" @click="testRobot">
        ¿Querés probar tu robot?
      </button>
    </div>

    </div>


  

  </div>
</template>


<script setup lang="ts">
import axios from "axios";

async function testRobot() {
  try {
    const respuesta = await axios.get("http://192.168.1.238/led");
    console.log(respuesta.data); 
  } catch (error) {
    console.error("Error al obtener datos:", error);
  }
}

</script>

<style scoped>


</style>
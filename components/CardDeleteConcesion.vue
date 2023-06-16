<template>
  <UCard :ui="{background: 'border-4 border-emerald-300', header: {background: 'bg-emerald-300', padding: 'py-3 px-4'}}">
    <template #header>
      <div class="w-18">
        <h1 class="text-xl font-semibold">Eliminar - Concesión</h1>
      </div>
    </template>
    <div>
      <div class="flex justify-center flex-wrap flex-col items-center">
        <UIcon name="i-heroicons-exclamation-triangle" class="flex justify-center w-12 h-12 text-red-600 "/>
        <h1 class="text-center text-2xl antialiased font-bold text-red-600">¡PRECAUCIÓN!</h1>
      </div>
      <h1 class="font-semibold mt-4">¿Desea eliminar la concesión seleccionada?</h1>
    </div>
    <div class="flex justify-center">
      
      <UButton size="lg" color="white" :ui="{
        base: 'mt-8 mr-4',
        color: {
          white: {
            solid: 'shadow-sm ring-2 ring-inset ring-gray-300  text-gray-900 bg-white hover:bg-gray-100 disabled:bg-white focus-visible:ring-2 focus-visible:ring-emerald-500 transition-all duration-1000 ease-in-out hover:transition-all hover:duration-1000 hover:ease-in-out focus-visible:transition-all focus-visible:duration-1000 focus-visible:ease-in-out '
          }
        }
      }" @click="closeModal"
      >Cancelar</UButton>
      <UButton size="lg" color="white" icon="i-heroicons-trash" :ui="{
        base: 'mt-8',
        color: {
          white: {
            solid: 'shadow-sm ring-2 ring-inset ring-red-300  text-red-900 bg-white hover:bg-red-100 disabled:bg-white focus-visible:ring-2 focus-visible:ring-emerald-500 transition-all duration-1000 ease-in-out hover:transition-all hover:duration-1000 hover:ease-in-out focus-visible:transition-all focus-visible:duration-1000 focus-visible:ease-in-out '
          }
        }
      }" @click="closeModal"
      >Eliminar</UButton>
    </div>
  </UCard>
</template>

<script setup>

const data = inject('sharedData');
const isAddOpen = inject('isAddOpen');
const id = ref('');
const nombre = ref('');
const estado = ref('');
const email = ref('');

const closeModal = () => {
  isAddOpen.value = false;
}
</script>
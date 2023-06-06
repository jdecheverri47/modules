<template>
  <UCard :ui="{background: 'border-4 border-emerald-300', header: {background: 'bg-emerald-300', padding: 'py-3 px-4'}}">
    <template #header>
      <div class="w-18">
        <h1 class="text-xl font-semibold">Agregar - Concesión</h1>
      </div>
    </template>


    <div>
      <div class="flex flex-wrap flex-row justify-center items-center gap-5">

        <div> 
          <div class="mb-4">
            <h2>Nombre</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput 
              type="text" 
              size="lg"
              variant="outline" 
              color="white"
              :ui="{
              color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 transition-all duration-600 ease-in-out'
                  }
                }
              }"
              v-model="nombre"
              />
              
            </div>
          </div>

          <div>
            <h2>Email</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="email"
              size="lg"
              variant="outline"
              color="white"
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              v-model="email" 
              />
            </div>
                  
          </div>
        </div>

        <div>
          <div class="mb-4">
            <h2>Código</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput 
              type="number" 
              name="ID" 
              size="lg" 
              variant="outline"
              color="white"
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              v-model="id"
              />
            </div>
          </div>

          <div>
            <h2>Estado</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <USelect 
              size="lg"
              :options="['Activo', 'Inactivo']"
              variant="outline" 
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              v-model="estado"
              />
            </div>    
          </div>
        </div>
      </div>
    </div>
          
    <div class="flex justify-end">
      
      <UButton size="lg" color="white" icon="i-heroicons-plus" :ui="{
        base: 'mt-8',
        color: {
          white: {
            solid: 'shadow-sm ring-2 ring-inset ring-emerald-300  text-emerald-900 bg-white hover:bg-emerald-50 disabled:bg-white focus-visible:ring-2 focus-visible:ring-emerald-500 transition-all duration-1000 ease-in-out hover:transition-all hover:duration-1000 hover:ease-in-out focus-visible:transition-all focus-visible:duration-1000 focus-visible:ease-in-out '
          }
        }
      }" @click="closeModal"
      >Agregar</UButton>
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
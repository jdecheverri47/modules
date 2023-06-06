<template>
  <UCard :ui="{background: 'border-4 border-emerald-300', header: {background: 'bg-emerald-300', padding: 'py-3 px-4'}}">
    <template #header>
      <div class="w-18">
        <h1 class="text-xl font-semibold">Editar - Plaza</h1>
      </div>
    </template>


    <div class="divide-y-2 gap-4">
      <div class="flex flex-wrap flex-row justify-center items-center gap-5">

        <div>
          <div class="mb-4">
            <h2>Concesión</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <USelect 
              size="lg"
              :options="['Autopista del Nordeste']"
              variant="outline" 
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              v-model="concesion"
              :disabled="concesionState"
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="concesionState = !concesionState"/>
            </div>    
          </div> 
        
          <div class="mb-4">
            <h2>Nombre</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput 
              type="text" 
              :placeholder="nombreStatic" 
              size="lg"
              variant="outline" 
              color="white"
              :disabled="nameState"
              :ui="{
              color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 transition-all duration-600 ease-in-out'
                  }
                }
              }"
              v-model="nombre"
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="nameState = !nameState"/>
            </div>
          </div>

          <div class="mb-6">
            <h2>Código</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput 
              type="number" 
              name="ID" 
              size="lg" 
              :placeholder="idStatic"
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
              :disabled="codigoState"
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="codigoState = !codigoState"/>
            </div>
          </div>
        </div>

        <div>
          <div class="mb-4">
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
              :disabled="estadoState"
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="estadoState = !estadoState"/>
            </div>    
          </div>

          <div class="mb-4">
            <h2>Longitud</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
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
              :disabled="longitudState"
              v-model="longitud" 
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="longitudState = !longitudState"
              />
            </div>
          </div>

          <div class="mb-6">
            <h2>Latitud</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
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
              :disabled="latitudState"
              v-model="latitud" 
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="latitudState = !latitudState"
              />
            </div>
          </div>
        </div>

      </div>

      <div class="flex flex-wrap flex-row justify-center items-center gap-5">
        <div>
          <div class="mb-4 mt-4">
            <h2>Cabinas Dinámicas</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
              size="lg"
              :placeholder="dinStatic"
              variant="outline" 
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              v-model="cabinasDin"
              :disabled="dinState"
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="dinState = !dinState"/>
            </div>    
          </div>

          <div class="mb-4">
            <h2>Cabinas Mixtas</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
              size="lg"
              :placeholder="mixStatic"
              variant="outline"
              color="white"
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              :disabled="mixState"
              v-model="cabinasMix" 
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="mixState = !mixState"
              />
            </div>
          </div>
        </div>
        
        <div>
          <div class="mb-4 mt-4">
            <h2>Cabinas Auxiliares</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
              size="lg"
              variant="outline"
              color="white"
              :placeholder="auxStatic"
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              :disabled="auxState"
              v-model="cabinasAux" 
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="auxState = !auxState"
              />
            </div>
          </div>

          <div class="mb-4">
            <h2>Cabinas Manuales</h2>
            <div class="flex flex-wrap flex-row gap-2">
              <UInput
              type="number"
              size="lg"
              :placeholder="manStatic"
              variant="outline"
              color="white"
              :ui="{
                color: {
                  white: {
                    outline: 'focus:ring-emerald-300 shadow-sm bg-white text-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 '
                  }
                }
              }"
              :disabled="manState"
              v-model="cabinasMan" 
              />
              <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="manState = !manState"
              />
            </div>
          </div>
        </div>
        
      </div>
    </div>
          
    <div class="flex justify-end">
      <button
        type="button"
        @click="closeModal"
        class="mt-8 inline-flex justify-center rounded-md border border-gray-400 bg-white px-4 py-2 text-sm
        font-semibold text-gray-900 hover:bg-blue-100 focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-200 focus-visible:ring-offset-2 focus-visible:transition-all focus-visible:duration-600 focus-visible:ease-in-out transition-all duration-600 ease-in-out hover:transition-all hover:duration-1000 hover:ease-in-out">
                  Guardar cambios
      </button>
    </div>
  </UCard>
</template>

<script setup>
const data = inject('sharedData');
const isEditOpen = inject('isEditOpen');
const id = ref('');
const nombre = ref('');
const estado = ref('');
const codigo = ref('');
const longitud = ref('');
const longitudState = ref(true);
const latitud = ref('');
const latitudState = ref(true);
const concesion = ref('');
const concesionState = ref(true);
const cabinasDin = ref('');
const mixState = ref(true);
const cabinasMix = ref('');
const auxState = ref(true);
const cabinasAux = ref('');
const manState = ref(true);
const cabinasMan = ref('');
const dinState = ref(true);
const nameState = ref(true);
const codigoState = ref(true);
const estadoState = ref(true);
const idStatic = data.arrayRows.value[data.indexValue.value].id;
const nombreStatic = data.arrayRows.value[data.indexValue.value].nombre;
const manStatic = data.arrayRows.value[data.indexValue.value].cabinasManuales;
console.log(manStatic);
const auxStatic = data.arrayRows.value[data.indexValue.value].cabinasAuxiliares;
const mixStatic = data.arrayRows.value[data.indexValue.value].cabinasMixtas;
const dinStatic = data.arrayRows.value[data.indexValue.value].cabinasDinamicas;
console.log(dinStatic);
const closeModal = () => {
  isEditOpen.value = false;
}
</script>
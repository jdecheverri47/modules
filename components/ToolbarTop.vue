<template>
  <ButtonGroupTb @changeModalState="() => isEditOpen = !isEditOpen"/>
  
  <UModal v-model="isEditOpen" :ui="{width: 'w-max'}">
      <UCard>
          <div class="divide-y divide-gray-200 dark:divide-gray-80 mb-5">
            <div class="w-18">
              <h1 class="text-xl font-semibold">Editar - Concesión</h1>
            </div>
          </div>

          <ModalConcesion v-if="currentRoute === '/concesion'" @datosEmitted="handleEvent"/>
          
          <div class="flex justify-end">
            <button
                  type="button"
                  class="mt-8 inline-flex justify-center rounded-md border border-gray-400 bg-white px-4 py-2 text-sm
                  font-semibold text-gray-900 hover:bg-blue-100 focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-200 focus-visible:ring-offset-2
                  focus-visible:transition-all focus-visible:duration-600 focus-visible:ease-in-out
                  transition-all duration-600 ease-in-out
                  hover:transition-all hover:duration-1000 hover:ease-in-out"

                  @click="closeModal"
                >
                  Guardar cambios
            </button>
          </div>
      </UCard>
  </UModal>
  
</template>

<script setup>

const isEditOpen = ref(false);
const route = useRoute();
const currentRoute = ref(route.path);
const id = ref('');
const nombre = ref('');
const estado = ref('');
const codigo = ref('');


const closeModal = () => {
  isEditOpen.value = false;
}

// const handleEvent = (datosEmitted) => {
//   id.value = datosEmitted.id;
//   console.log(id.value);
//   nombre.value = datosEmitted.nombre;
//   console.log(nombre.value);
//   estado.value = datosEmitted.estado;
//   console.log(estado.value);
//   codigo.value = datosEmitted.codigo;
//   console.log(codigo.value);
// };
</script>
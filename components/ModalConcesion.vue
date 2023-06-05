<template>
  <div class="flex flex-wrap flex-row justify-center items-center gap-5">
    <div> 
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
            <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="nameState = !nameState"
            />
          </div>
          
      </div>
      <div >
        <h2>Email</h2>
        <div class="flex flex-wrap flex-row gap-2">
          <UInput
          type="email"
          :placeholder="emailStatic"
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
          :disabled="emailState"
          v-model="email" 
          />
          <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="emailState = !emailState"
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
          <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="codigoState = !codigoState"
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
          :disabled="estadoState"
          />
          <UButton icon="i-heroicons-pencil-square" size="md" color="white" square variant="solid" @click="estadoState = !estadoState"
          />
        </div>    
        
      </div>
    </div>
  </div>
  
</template>

<script setup>

const data = inject('sharedData');

const id = ref('');
const nombre = ref('');
const email = ref('');
const estado = ref('');
const nameState = ref(true);
const emailState = ref(true);
const codigoState = ref(true);
const estadoState = ref(true);
const datosEmit = ref({});


const idStatic = data.arrayRows.value[data.indexValue.value].id;
const nombreStatic = data.arrayRows.value[data.indexValue.value].nombre;
const emailStatic = data.arrayRows.value[data.indexValue.value].email;

// onMounted(() => {
//   const datosEmitted = {
//     id: id.value,
//     nombre: nombre.value,
//     email: email.value,
//     estado: estado.value
//   }
//   emit('datosEmitted', datosEmitted);
// }) 
</script>
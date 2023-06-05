<template>
  <div class="flex justify-center mt-5">
       <div class="overflow-auto rounded-lg border-2 border-emerald-300 shadow w-fit">
           <table class="bg-zinc-50 table-fixed">
               <thead class="border-b shadow">
                   <tr>
                       <th v-for="col in columns" class="py-3 px-8 justify-center text-md font-semibold text-left bg-emerald-300" :key="col.name" >
                           <div v-if="col.align === 'center'" class="text-center">
                                {{ col.label }}
                           </div>
                           <div v-else>
                                 {{ col.label }}
                           </div>
                       </th>
                   </tr>
                  </thead>
               <tbody>
                   <tr v-for="(row, index) in rows" :key="row.codigo"  @click="seleccionarFila(index)" :class="{ 'bg-stone-200 transition-all duration-500 ease-in-out': filaSeleccionada === index, 'bg-zinc-50 transition-all duration-500 ease-in-out hover:bg-slate-200' : filaSeleccionada !== index}" >
                       <td class="py-3 px-8 justify-center text-md text-gray-700 select-none cursor-pointer" v-for="column in columns" :key="column.name" >
                           <div v-if="column.name === 'estado'" class="text-center">
                               <span v-if="row[column.field] === 'Activo'" class="px-2 inline-flex text-xs text-center leading-5 font-semibold rounded-full bg-green-100 text-green-800 border border-gray-400">
                                   {{ row[column.field] }}
                               </span>
                               <span v-else class="px-2 inline-flex text-center text-xs leading-5 font-semibold rounded-full bg-red-100 text-red-800 border border-gray-400">
                                   {{ row[column.field] }}
                               </span>
                           </div>
                           <div 
                            v-else-if="column.align === 'center'" 
                                class="text-center">
                            {{ row[column.field] }}
                           </div>
                           <div v-else>
                               {{ row[column.field] }}
                           </div>   
                       </td>
                        
                   </tr>
               </tbody>
              </table>
       </div>  
  </div>
</template>

<script setup>
const data = inject('sharedData');
const columns = ref(data.arrayColumns);
const rows = ref(data.arrayRows);
const emit = defineEmits(['indexSelected']);

const filaSeleccionada = ref(null);

const seleccionarFila = (index) => {
   if (filaSeleccionada.value === index) {
      filaSeleccionada.value = null;
      emit('indexSelected', null);

  } else {
      filaSeleccionada.value = index;
      emit('indexSelected', index);

  }
};

</script>

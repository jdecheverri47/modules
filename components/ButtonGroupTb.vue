<template>
  <div class="bg-gray-200 p-2 flex justify-center gap-3 shadow-inner">
      <UButton label="Edit" color="white" icon="i-heroicons-pencil-square" :disabled="data.indexValue.value === null" @click="$emit('changeModalState')" :ui="{
          color: {
              white: {
                  solid: 'bg-neutral-100 border border-gray-300 hover:border-slate-300 hover:bg-slate-200 hover:transition-all hover:duration-400 hover:ease-in-out transition-all duration-400 ease-in-out'
              }
          }
      }"/>

      <UButton label="Add" color="white" icon="i-heroicons-plus-solid" :ui="{
                  color: {
                      white: {
                          solid: 'bg-neutral-100 border border-gray-300 hover:border-slate-300 hover:bg-slate-200 hover:transition-all hover:duration-400 hover:ease-in-out transition-all duration-400 ease-in-out'
                      }
                  }
              }"/>

      <UButton label="Delete" color="red" icon="i-heroicons-trash" class="text-red-500 hover:shadow-sm hover:shadow-red-200" :ui="{
          color: {
              red: {
                  solid: 'bg-neutral-100 border border-red-300 hover:border-red-300 hover:bg-red-200 hover:transition-all hover:duration-400 hover:ease-in-out transition-all duration-400 ease-in-out'
              }
          }
      }"/>
  </div>
</template>

<script setup>
const data = inject('sharedData');
console.log(data.indexValue.value)
</script>
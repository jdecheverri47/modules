<template>
  <UVerticalNavigation 
  :links="links" 
  class="text-lg" 
  :ui="{
    padding: 'p-4', 
    size: 'text-xl', 
    active: 'rounded-none bg-stone-200 text-gray-950',
    inactive: 'active:bg-gray-50 text-gray-800 hover:text-gray-50 hover:bg-gray-950 transition-all hover:duration-800 active:text-gray-950 hover:transition all',
    icon: {
      base: 'flex-shrink-0 w-4 h-4',
      active: 'text-gray-800',
      inactive: 'text-gray-800 group-hover:text-gray-50 group-active:text-gray-950'
      },
    rounded: 'rounded-none'
    }" />
</template>

<script setup>
const links = [
  {
    label: 'Concesion',
    icon: 'i-heroicons-envelope',
    to: '/concesion'
  }, 
  {
    label: 'Plaza',
    icon: 'i-heroicons-receipt-percent',
    to: '/plaza'
  }, 
  {
    label: 'Pista',
    icon: 'i-heroicons-rss',
    to: '/pista'
  }, 
  {
    label: 'Imagenes',
    icon: 'i-heroicons-photo',
    to: '/imagenes'
  }
]
</script>



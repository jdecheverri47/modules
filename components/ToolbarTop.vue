<template>
  <ButtonGroupTb @changeModalState="() => isEditOpen = !isEditOpen" @changeAddState="() => isAddOpen = !isAddOpen" @changeDeleteState="() => isDeleteOpen = !isDeleteOpen"/>
  
  <UModal v-model="isEditOpen" :ui="{width: 'w-max'}">
    
    <CardConcesion v-if="currentRoute === '/concesion'"/>

    <CardPlaza v-if="currentRoute === '/plaza'"/>
        
  </UModal>

  <UModal v-model="isAddOpen" :ui="{width: 'w-max'}">
    
    <CardAddConcesion v-if="currentRoute === '/concesion' "/>

    <!-- <CardAddPlaza v-if="currentRoute === '/plaza'"/> -->
        
  </UModal>
  
  <UModal v-model="isDeleteOpen" :ui="{width: 'w-max'}">
    
    <CardDeleteConcesion v-if="currentRoute === '/concesion' "/>

    <!-- <CardAddPlaza v-if="currentRoute === '/plaza'"/> -->
        
  </UModal>
</template>

<script setup>
const isEditOpen = ref(false);
const isAddOpen = ref(false);
const isDeleteOpen = ref(false);
const route = useRoute();
const currentRoute = ref(route.path);

provide('isEditOpen', isEditOpen);
provide('isAddOpen', isAddOpen);
provide('isDeleteOpen', isDeleteOpen);
</script>
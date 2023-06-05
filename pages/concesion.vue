<template>
  <div>
    <ToolbarTop />
  </div>
  <div>
    <Tabla @indexSelected="(value) => { 
    indexValue = value
    console.log(indexValue)
    }" />
  </div>
</template>
  
<script setup>

const indexValue = ref(null);
const columns = ref([
  {
    name: 'codigo',
    label: 'Código',
    align: 'center',
    field: 'id',
    sortable: true
  },
  {
    name: 'nombre',
    label: 'Nombre',
    align: 'left',
    field: 'nombre',
    sortable: true
  },
  {
    name: 'email',
    label: 'Email',
    align: 'left',
    field: 'email',
    sortable: true
  },
  {
    name: 'estado',
    label: 'Estado',
    align: 'center',
    field: 'estado',
    sortable: true
  },
]);
  
const rows = ref([
  {
    id: '00001',
    nombre: 'Juan Calvino',
    email: 'juancalvino@gmail.com',
    estado: 'Activo'
  },
  {
    id: '00002',
    nombre: 'Nikola Tesla',
    email: 'nikolat@gmail.com',
    estado: 'Activo'
  },
  {
    id: '00003',
    nombre: 'Leonardo Da Vinci',
    email: 'davincileo@gmail.com',
    estado: 'Inactivo'
     },
     {
    id: '00004',
    nombre: 'Abraham Lincoln',
    email: 'abrahaml@gmail.com',
    estado: 'Activo'
  }
]);

const dataConcesion = toRefs(reactive({ 
  arrayColumns: columns, 
  arrayRows: rows, 
  indexValue: indexValue 
}))


provide('sharedData', dataConcesion);

</script>
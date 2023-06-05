<template>
  <div>
    <ToolbarTop/>
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
    name: 'concesion',
    label: 'Concesión',
    align: 'center',
    field: 'concesion',
    sortable: true
  },
  {
    name: 'plaza',
    label: 'Plaza',
    align: 'center',
    field: 'plaza',
    sortable: true
  },
  {
    name: 'codigo',
    label: 'Código',
    align: 'center',
    field: 'codigo',
    sortable: true
  },
  
  {
    name: 'nombre',
    label: 'Nombre',
    align: 'center',
    field: 'nombre',
    sortable: true
  },
  {
    name: 'orden',
    label: 'Orden',
    align: 'center',
    field: 'orden',
    sortable: true
  },
  {
    name: 'estado',
    label: 'Estado',
    align: 'center',
    field: 'estado',
    sortable: true
  }
]);

const rows = ref([
  {
    concesion: 'Autopista del Nordeste',
    plaza: 'Peaje Zaragoza',
    codigo: 5674321001,
    nombre: 'Carril 1',
    orden: 1,
    estado: 'Activo'
  },
  {
    concesion: 'Autopista del Nordeste',
    plaza: 'Peaje Zaragoza',
    codigo: 5674321002,
    nombre: 'Carril 2',
    orden: 1,
    estado: 'Activo'
  },
  {
    concesion: 'Autopista del Nordeste',
    plaza: 'Peaje Zaragoza',
    codigo: 5674321003,
    nombre: 'Carril 3',
    orden: 1,
    estado: 'Inactivo'
  },
  {
    concesion: 'Autopista del Nordeste',
    plaza: 'Peaje Zaragoza',
    codigo: 5674321004,
    nombre: 'Carril 4',
    orden: 1,
    estado: 'Activo'
  },
  
]);

const dataPista = toRefs(reactive({
  arrayColumns: columns,
  arrayRows: rows,
  indexValue: indexValue 
}));

provide('sharedData', dataPista);
</script>
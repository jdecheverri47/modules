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
    name: 'cabinasManuales',
    label: 'Cabinas Manuales',
    align: 'center',
    field: 'cabinasManuales',
    sortable: true
  },
  {
    name: 'cabinasDinamicas',
    label: 'Cabinas Dinamicas',
    align: 'center',
    field: 'cabinasDinamicas',
    sortable: true
  },
  {
    name: 'cabinasMixtas',
    label: 'Cabinas Mixtas',
    align: 'center',
    field: 'cabinasMixtas',
    sortable: true
  },
  {
    name: 'cabinasAuxiliares',
    label: 'Cabinas Auxiliares',
    align: 'center',
    field: 'cabinasAuxiliares',
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
    id: 1,
    nombre: 'Juan Calvino',
    cabinasManuales: 2,
    cabinasDinamicas: 4,
    cabinasMixtas: 4,
    cabinasAuxiliares: 6,
    estado: 'Activo'
  },
  {
    id: 2,
    nombre: 'Nikola Tesla',
    cabinasManuales: 9,
    cabinasDinamicas: 5,
    cabinasMixtas: 3,
    cabinasAuxiliares: 2,
    estado: 'Inactivo'
  },
  {
    id: 3,
    nombre: 'Albert Einstein',
    cabinasManuales: 2,
    cabinasDinamicas: 2,
    cabinasMixtas: 2,
    cabinasAuxiliares: 2,
    estado: 'Activo'
  },
  {
    id: 4,
    nombre: 'Isaac Newton',
    cabinasManuales: 10,
    cabinasDinamicas: 8,
    cabinasMixtas: 6,
    cabinasAuxiliares: 4,
    estado: 'Inactivo'
  },
  {
    id: 5,
    nombre: 'Galileo Galilei',
    cabinasManuales: 0,
    cabinasDinamicas: 1,
    cabinasMixtas: 2,
    cabinasAuxiliares: 0,
    estado: 'Activo'
  },
  {
    id: 6,
    nombre: 'Marie Curie',
    cabinasManuales: 3,
    cabinasDinamicas: 1,
    cabinasMixtas: 8,
    cabinasAuxiliares: 10,
    estado: 'Activo'
  },
  {
    id: 7,
    nombre: 'Charles Darwin',
    cabinasManuales: 5,
    cabinasDinamicas: 2,
    cabinasMixtas: 1,
    cabinasAuxiliares: 8,
    estado: 'Activo'
  },
  {
    id: 8,
    nombre: 'Stephen Hawking',
    cabinasManuales: 2,
    cabinasDinamicas: 2,
    cabinasMixtas: 6,
    cabinasAuxiliares: 2,
    estado: 'Inactivo'
  }
]);

const dataPlaza = toRefs(reactive({
  arrayColumns: columns,
  arrayRows: rows,
  indexValue: indexValue 
}));

provide('sharedData', dataPlaza);
</script>
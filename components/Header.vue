<template>
    <header class="bg-white shadow">
      <nav class="mx-3 flex max-w-10xl items-center justify-center justify-items-center p-2 lg:px-8" aria-label="Global">
        <div class="hidden lg:flex lg:flex-1">
            <UButton @click="isOpen = true" color="black" icon="i-heroicons-bars-3" :ui="{
              color: {
                black: {
                  solid: 'shadow-sm text-white bg-gray-900 hover:bg-gray-800 disabled:bg-gray-900 dark:bg-white focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500',
                  link: 'text-gray-900 underline-offset-4 hover:underline focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500'
                }
              }
            }"/>
            <USlideover v-model="isOpen" side="left" 
            :ui="{
                background: 'bg-emerald-300',
            }   
            ">
            <StackedList />
            </USlideover>
        </div>
        <div class="flex lg:flex-1 justify-center">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Your Company</span>
            <img class="h-14 w-auto" src="../assets/images/C505EF1B-28CA-4FD4-A240-D5AFBBC9989A-removebg.png" alt="" />
          </a>
        </div>
        <div class="flex lg:flex-1 justify-end">
          <img class="inline-block h-12 w-12 rounded-full ring-2 ring-black" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
        </div>
      </nav>
    </header>
</template>
  
<script setup>
    const isOpen = ref(false);

</script>
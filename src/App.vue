<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

const menuIsOpen = ref(false)

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>
  <header>
    <nav class="bg-indigo-900">
      <ul class="flex justify-between p-5">
        <li>
          <RouterLink to="/" class="text-gray-50"> Accueil </RouterLink>
        </li>
        <li>
          <button @pointerdown="menuIsOpen = !menuIsOpen"
            aria-controls="mainNav"
            aria-expanded="true"
            class="rounded-full border-2 border-sky-50 bg-indigo-500 text-gray-50 px-2 w-20"
          >
          menu
        </button>
        </li>
      </ul>
    </nav>
  </header>
  <body class="bg-indigo-500 text-gray-50 h-screen p-4">
    <Transition
        class="transition-transform duration-1000"
        enter-from-class="-translate-x-full"
        enter-to-class="translate-x-0"
        leave-active-class="-translate-x-full"
      >
      <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
      <nav v-show="menuIsOpen" id="mainNav">
        <ul class="grid gap-4 bg-indigo-700 p-2 w-24 mb-6">
          <li><RouterLink to="/Accordeon"> Accordéon </RouterLink></li>
          <li><RouterLink to="/Boucle"> Boucle </RouterLink></li>
          <li><a href="#">item 3</a></li>
        </ul>
      </nav>
      </Transition>
    <RouterView v-slot="{ Component }">
      <Suspense>
        <component :is="Component" />
      </Suspense>
    </RouterView>
  </body>
</template>

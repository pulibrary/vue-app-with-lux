<script setup>
import {LuxLibraryHeader, LuxMenuBar} from 'lux-design-system'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <lux-library-header app-name="A cool vue app" abbr-name="LTR" app-url="https://catalog.princeton.edu" theme="dark">
      <lux-menu-bar type="main-menu" :menu-items="[
          {name: 'Help', component: 'Help', href: '/help/'},
          {name: 'Feedback', component: 'Feedback', href: '/feedback/'},
          {name: 'Your Account', component: 'Account', href: '/account/', children: [
            {name: 'Logout', component: 'Logout', href: '/account/'}
          ]}
        ]"
      ></lux-menu-bar>
    </lux-library-header>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue + Lux" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

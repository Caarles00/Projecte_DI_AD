<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Qualificacions App
        </q-toolbar-title>

        <div>{{ fecha }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'My GitHub',
    caption: 'Caarles00',
    icon: 'school',
    link: 'https://github.com/Caarles00'
  },
  {
    title: 'Login',
    caption: 'Window login',
    icon: 'login',
    class: 'login'
  },
  {
    title: 'About',
    caption: 'About me',
    icon: 'person',
    link: 'http://localhost:8080/#/about'
  }
]

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  },
  computed: {
    fecha () {
      const mesos = ['Gener', 'Febrer', 'Març', 'Abril', 'Maig', 'Juny', 'Juliol', 'Agost', 'Septembre', 'Octubre', 'Novembre', 'Desembre']
      const hui = new Date()
      const diaSetmana = hui.toLocaleDateString('ca-CA', { weekday: 'long' })
      const diaSetmanaMayus = diaSetmana.charAt(0).toUpperCase() + diaSetmana.slice(1)
      return diaSetmanaMayus + ', ' + hui.getDate() + ' de ' + mesos[hui.getMonth()] + ' de ' + hui.getFullYear()
    }
  }
  
})
</script>


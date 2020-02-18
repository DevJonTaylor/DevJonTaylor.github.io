<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          icon="menu"
          aria-label="Menu"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">Essential Links</q-item-label>
        <nav-tab
          v-for="link in links"
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
import NavTab from 'components/NavTab'

export default {
  name: 'MainLayout',

  components: { NavTab },

  data () {
    return {
      leftDrawerOpen: false,
      links: [
        {
          title: 'About Me',
          icon: 'user-check',
          link: '/',
          color: 'primary'
        },
        {
          title: 'Process',
          icon: 'tasks',
          link: '/process',
          color: 'secondary'
        },
        {
          title: 'Clients',
          icon: 'users',
          link: '/clients',
          color: 'accent'
        }
      ]
    }
  }
}
</script>

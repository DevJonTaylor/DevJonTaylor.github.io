<template>
  <q-item clickable v-ripple:primary tag="div" class="nav-tab" :class="`bg-${color}`" @click="newPage(link)">
    <q-item-section v-if="icon" avatar>
      <q-icon :name="`fas fa-${icon}`" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: 'NavTab',
  props: {
    title: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      default: '#'
    },
    icon: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: ''
    }
  },
  methods: {
    newPage(link) {
      console.log(link)
      return link === this.$route.path ? null : this.$router.push({path: link});
    }
  },
  computed: {
    isActive() {
      return (this.$route.path === this.props.link) === true ? 'is-active' : '';
    }
  }
}
</script>



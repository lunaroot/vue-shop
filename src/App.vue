<template>
  <component :is="layout + '-layout'" v-if="layout" />
</template>

<script>
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import MainLayout from './layout/MainLayout'
import AuthLayout from './layout/AuthLayout'
import NotFoundLayout from './layout/NotFoundLayout'

export default {
  setup() {
    const route = useRoute()

    return {
      layout: computed(() => route.meta.layout)
    }
  },
  components: {
    MainLayout,
    AuthLayout,
    NotFoundLayout
  }
}
</script>

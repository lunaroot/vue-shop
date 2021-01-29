<template>
  <AppLoader v-if="loading" />
  <AppPage title="Страница не найдена" :back="true" v-else />
</template>

<script>
import { ref, computed, onMounted } from 'vue'
import { useStore}  from 'vuex'
import AppLoader from '../components/AppLoader'
import AppPage from '../components/AppPage'

export default {
  setup() {
    const store = useStore()
    const loading = ref(false)

    onMounted(async () => {
      loading.value = true
      await store.dispatch('load')
      loading.value = false
    })

    return {
      loading
    }
  },
  components: {
    AppPage,
    AppLoader
  }
}
</script>

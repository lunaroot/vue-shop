<template>
  <AppLoader v-if="loading" />
  <app-page title="Список товаров" v-else>
    <!-- <template #header>
      <p>Home page</p>
    </template> -->
  </app-page>
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

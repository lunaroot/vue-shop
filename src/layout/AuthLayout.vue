<template>
  <div class="container">
    <AppMessage />
    <router-view />
  </div>
</template>

<script>
import AppMessage from '../components/AppMessage'

export default {
  components: {
    AppMessage
  }
}
</script>

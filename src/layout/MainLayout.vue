<template>
  <TheNavbar />
  <TheSidebar />
  <div class="container with-nav">
    <AppMessage />
    <router-view />
  </div>
</template>

<script>
import TheNavbar from '../components/TheNavbar'
import TheSidebar from '../components/TheSidebar'
import AppMessage from '../components/AppMessage'

export default {
  components: {
    TheNavbar,
    AppMessage,
    TheSidebar
  }
}
</script>

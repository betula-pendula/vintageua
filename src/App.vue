<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <Contacts msg="Anton" />
    <OurOffices />
    <ContactUs />
  </div>
</template>

<script>
import Contacts from './components/Contacts.vue'
import OurOffices from './components/OurOffices.vue'
import ContactUs from './components/ContactUs.vue'

export default {
  name: 'app',
  components: {
    Contacts,
    OurOffices,
    ContactUs
  }
}
</script>

<style>
#app {
  top: 0;
}
</style>

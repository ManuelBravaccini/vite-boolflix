<script>
import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'AppVue',

  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },

  data() {
    return {
      store
    }
  },
}
</script>

<template>
  <AppHeader />
  <AppMain />
  <AppFooter />
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;
</style>

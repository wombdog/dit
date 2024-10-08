<template>
  <nav>
    <Header></Header>
    <SettingsSlider></SettingsSlider>

  </nav>
  <router-view/>
</template>

<script>
  import Header from '@/components/Header.vue'
import SettingsSlider from '@/components/SettingsSlider.vue';
  export default {
    components: {
        Header,
        SettingsSlider
      }
  }


</script>

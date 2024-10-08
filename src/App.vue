<template>
  <nav>
    <Header></Header>
    <DraggableWindow></DraggableWindow>
    

  </nav>
  <router-view/>
</template>

<script>
  import Header from '@/components/Header.vue'
  import DraggableWindow from './components/DraggableWindow.vue';
  export default {
    components: {
        Header,
        DraggableWindow
      }
  }


</script>

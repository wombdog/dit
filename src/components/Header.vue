<template>
    <header>
        <div class="header_text">DITHER</div>
    </header>
</template>

<script>
    export default{
        name: 'Header',
    }
</script>

<style scoped>

  @font-face {
    font-family: 'CustomFont'; /* Name your font family */
    src: url('/Users/mw/Library/Fonts/Blur Bold.otf'); /* Locate the .ttf file within your directory*/
  }

  body{
    background-color: #f2f2f2;
    margin: 0;
  }
  header {
    position: sticky;    
  }
  .header_text{
    font-family:CustomFont;
    text-align: left;
    color: black;
    padding: 20px;
    font-size: 2rem;
    display: flex;
    justify-content: center;
  }
</style>

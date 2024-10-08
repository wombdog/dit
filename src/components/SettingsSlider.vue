<template>
    <div v-for="slider in sliders" :kex = "index" class="slidecontainer">
        <div class="textbox">{{ slider }}</div>
        <input 
            type="range" 
            min="1" 
            max="100" 
            value="50" 
            class="slider" 
            id="'slider' + index"
        >
    </div>
</template>

<script>
    export default{
        name: 'SettingsSlider',
        data() {
            return {
                sliders: ['Gamma', 'Brightness', 'Contrast', 'Weight', 'Clarity']
            }
        }
    }
</script>

<style>

.textbox{
    font-family: Arial, Helvetica, sans-serif;
    width: 30%;
    padding-left: 5%;
    color: #f4eded;
}

.slidecontainer{
    background-color: rgb(74, 74, 74);
    height: 1.5rem;
    width: 300px; 
    padding-right: 5%;
    display: flex;
    align-items: center;
    gap: 10px;
    -webkit-transition: .2s; /* 0.2 seconds transition on hover */
    transition: opacity .2s;
}

.slidecontainer:hover{
    opacity: 0.95;
    cursor: pointer;
}

.slider:hover {
  background-color: rgb(102, 227, 206);
  cursor: pointer;

}
.slider {
  background-color: #bebebe;
  appearance: none;
  width:70%; /* Full-width */
  height: 2px; /* Specified height */
  outline: none; /* Remove outline */
  -webkit-transition: .2s; /* 0.2 seconds transition on hover */
  transition: background-color .2s;
}
.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 20px;
  height: 20px;
  background: #bebebe;
  border-radius: 5px;
  cursor: pointer;
}

</style>
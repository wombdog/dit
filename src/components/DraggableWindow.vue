<template>
    <div id="draggableHeader">
        <div id="windowHeader">
            <img class = "image" :src="imgPath" alt="logo">
        </div>
        <SettingsSlider></SettingsSlider>
        <div class = "footer"></div>
    </div>
</template>

<script>
import SettingsSlider from '@/components/SettingsSlider.vue';

export default {
  name: 'DraggableWindow',
  components: {
    SettingsSlider,
  },
  data() {
    return {
      imgPath: require('@/assets/menu_icon.png') // Use relative path
    };
  },
  mounted() {
    // Call dragElement only when the component is mounted
    this.dragElement(document.getElementById("draggableHeader"));
  },
  methods: {
    dragElement(elmnt) {
      var pos1 = 0, pos2 = 0, pos3 = 0, pos4 = 0;
      
      // Restrict dragging to the window header
      const header = document.getElementById("windowHeader");
      if (header) {
        header.onmousedown = dragMouseDown;
      }

      function dragMouseDown(e) {
        e = e || window.event;
        e.preventDefault();

        // Get the initial cursor position
        pos3 = e.clientX;
        pos4 = e.clientY;

        document.onmouseup = closeDragElement;
        document.onmousemove = elementDrag;
      }

      function elementDrag(e) {
        e = e || window.event;
        e.preventDefault();
        
        // Calculate new cursor position
        pos1 = pos3 - e.clientX;
        pos2 = pos4 - e.clientY;
        pos3 = e.clientX;
        pos4 = e.clientY;

        // Set the new position of the element
        elmnt.style.top = (elmnt.offsetTop - pos2) + "px";
        elmnt.style.left = (elmnt.offsetLeft - pos1) + "px";
      }

      function closeDragElement() {
        document.onmouseup = null;
        document.onmousemove = null;
      }
    }
  }
};
</script>

<style>
#windowHeader {
    height: 1.5rem;
    width: 300px;
    background-color: rgb(53, 53, 53);
    padding-right: 5%;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;


    display: flex; /* Flexbox for centering */
    align-items: center; /* Vertical centering */
    justify-content: left; /* Horizontal alignment to the left */
    text-align: right;
}

#draggableHeader {
    position: absolute;
    height: fit-content;
    width: fit-content;
}
.image {
    scale: 0.4;
    display: inline-block;
    cursor: pointer;
}

.footer{
    background-color: rgb(53, 53, 53);
    height: 0.8rem;
    width: 300px;
    padding-right: 5%;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
}
</style>

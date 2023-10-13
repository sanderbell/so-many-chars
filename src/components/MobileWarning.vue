<template>
    <div id="mobile-warning">
        <img draggable="false" :src="image" />
        <h1>Please open this site on desktop</h1>
    </div>
</template>
  
<script>
import image from "../assets/pinch.png";

export default {
    data: function () {
        return {
            image: image
        };
    }
};
</script>
  

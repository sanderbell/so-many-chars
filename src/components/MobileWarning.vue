<template>
    <div id="mobile-warning">
        <img draggable="false" :src="pinch" />
        <h1>Please open this site on a larger screen</h1>
    </div>
</template>
  
<script>
import pinch from "../assets/pinch.png";

export default {
    data: function () {
        return {
            image: pinch
        };
    }
};
</script>
  

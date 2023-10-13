<template>
  <div id="app">
    <MobileWarning />
    <TextCounter />
  </div>
</template>

<script>
import MobileWarning from './components/MobileWarning.vue';
import TextCounter from './components/TextCounter.vue';

export default {
  components: {
    TextCounter,
    MobileWarning
},
};
</script>
<template>
    <button v-if="scrollTop" @click="$emit('scroll-to-top')" class="scroll-top">
    ↑
  </button>
</template>

<script>
export default {
    name: 'ScrollTop',
    props: ['scrollTop']
};
</script>
<template>
</template>

<script>

export default {
    props: ['url','latlng'],
    mounted() {
      this.$imageOverlay = L.ImageOverlay(this.url, this.latlng);
    },
    methods: {
      deferredMountedTo(parent) {
        this.$imageOverlay.addTo(parent);
        _.forEach(this.$children, (child) => {
          child.deferredMountedTo(that);
        });
      }
    }
};
</script>

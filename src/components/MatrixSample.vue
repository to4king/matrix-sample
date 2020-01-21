<template>
  <div class="area" v-on:click.once="getPosition()"></div>
</template>

<script>
export default {
  name: 'MatrixSample',
  props: {
    msg: String
  },
  methods: {
    getPosition: function () {
      document.addEventListener('mousemove', function(e) {
        const _X = e.pageX;
        const _Y = e.pageY;
        alert(`X: ${_X}, Y: ${_Y}`);
      });
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.area {
  min-height: 50em;
  min-width: 50em;
  background-color: #777733;
}
</style>

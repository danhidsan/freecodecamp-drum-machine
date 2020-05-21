<template>
  <div class="container">
    <div class="row">
      <DrumPadButton letter="Q" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="W" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="E" v-on:onClick="onClickPadButton"/>
    </div>
    <div class="row">
      <DrumPadButton letter="A" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="S" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="D" v-on:onClick="onClickPadButton"/>
    </div>
    <div class="row">
      <DrumPadButton letter="Z" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="X" v-on:onClick="onClickPadButton"/>
      <DrumPadButton letter="C" v-on:onClick="onClickPadButton"/>
    </div>
  </div>
</template>

<script>
import DrumPadButton from './DrumPadButton'
export default {
  name: "DrumPad",
  components: {
    DrumPadButton
  },
  methods: {
    onClickPadButton: function (letter) {
      this.$emit('onClick', letter)
    }
  }
}
</script>

<style scoped>

.container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}


</style>
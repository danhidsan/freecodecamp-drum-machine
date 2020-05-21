<template>
  <div id="drum-machine" class="drum-machine">
    <div class="pad-container">
      <DrumPad v-on:onClick="handleClickDrumPadButton"/>
    </div>
    <div class="controls-container">
      <!-- Put controls component here -->
      <Controls
              :text="keycap"
              :power="power"
              :bank="bank"
              :volume="volume"
      />
    </div>
  </div>
</template>

<script>
import DrumPad from './DrumPad'
import Controls from "./Controls";
export default {
  name: 'DrumMachine',
  components: {
    DrumPad,
    Controls
  },
  data() {
    return {
      keycap: "",
      power: true,
      bank: false,
      volume: 25
    }
  },
  methods: {
    handleClickDrumPadButton(keycap) {
      this.keycap = keycap
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.drum-machine {
  width: 600px;
  height: 300px;
  background-color: lightsalmon;
  padding: 15px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.pad-container {
  width: 55%; 
  height: 100%;
}

.controls-container {
  width: 40%; 
  height: 100%;
}
</style>

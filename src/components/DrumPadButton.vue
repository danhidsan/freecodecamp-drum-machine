<template>
  <div v-bind:ref="letter" v-bind:class="buttonStyle" @click="handleClickButton(letter)">
    <span>{{ letter }}</span>
  </div>
</template>

<script>
export default {
  name: "DrumPadButton",
  props: {
    letter: String,
    onClick: Function
  },
  data() {
    return {
      buttonStyle: 'drum-pad'
    }
  },
  methods: {
    handleClickButton: function (letter) {
      this.$emit('onClick', letter)
    },
    handleKeyDown: function (event) {
      if (event.key === this.letter.toLowerCase()) {
        this.buttonStyle = 'drum-pad-active'
        this.handleClickButton(this.letter)
        setTimeout(() => this.buttonStyle = 'drum-pad', 100)
      }
    }
  },
  mounted() {
    window.addEventListener('keydown', this.handleKeyDown)
  }
}
</script>

<style scoped>
.drum-pad {
  width: 100px;
  height: 90px;
  background-color: #7ad9ff;
  cursor: pointer;
  box-shadow: 3px 5px gray;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}

.drum-pad-active {
  width: 100px;
  height: 90px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  background-color: #ffc4ad;
  box-shadow: 0 2px gray;
  transform: translateY(3px);
}

.drum-pad:hover {
  background-color: #ffc4ad
}

.drum-pad:active {
  background-color: #ffc4ad;
  box-shadow: 0 2px gray;
  transform: translateY(3px);
}
</style>
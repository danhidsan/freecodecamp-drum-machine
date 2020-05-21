<template>
    <div class="controls">
        <label class="switch">
            <input type="checkbox" v-bind:checked="power" v-on:change="handleChangePower">
            <span class="slider"></span>
        </label>
        <div class="display">
            <span>{{ text }}</span>
        </div>
        <input type="range" min="1" max="100" v-bind:value="volume" class="volume" id="myRange" v-on:change="handleChangeVolume">
        <label class="switch">
            <input type="checkbox" v-bind:checked="bank" v-on:change="handleChangeBank">
            <span class="slider"></span>
        </label>
    </div>
</template>

<script>
    export default {
      name: "Controls",
      props: {
        power: Boolean,
        bank: Boolean,
        text: String,
        volume: Number
      },
      methods: {
        handleChangePower(event) {
          this.$emit('changePower', event.target.value)
        },
        handleChangeBank(event) {
          this.$emit('changeBank', event.target.value)
        },
        handleChangeVolume(event) {
          this.$emit('changeVolume', event.target.value)
        }
      }
    }
</script>

<style scoped>
    .controls {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }
    .display {
        background-color: #cccccc;
        width: 200px;
        height: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .volume {
        -webkit-appearance: none;
        width: 100%;
        height: 25px;
        background: #d3d3d3;
        outline: none;
        opacity: 0.7;
        -webkit-transition: .2s;
        transition: opacity .2s;
    }

    .volume:hover {
        opacity: 1;
    }

    .volume::-webkit-slider-thumb {
        -webkit-appearance: none;
        appearance: none;
        width: 25px;
        height: 25px;
        background: #4CAF50;
        cursor: pointer;
    }

    .volume::-moz-range-thumb {
        width: 25px;
        height: 25px;
        background: #4CAF50;
        cursor: pointer;
    }

    .switch {
        position: relative;
        display: inline-block;
        width: 60px;
        height: 34px;
    }

    .switch input {
        opacity: 0;
        width: 0;
        height: 0;
    }

    .slider {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #ccc;
        -webkit-transition: .4s;
        transition: .4s;
    }

    .slider:before {
        position: absolute;
        content: "";
        height: 26px;
        width: 26px;
        left: 4px;
        bottom: 4px;
        background-color: white;
        -webkit-transition: .4s;
        transition: .4s;
    }

    input:checked + .slider {
        background-color: #2196F3;
    }

    input:focus + .slider {
        box-shadow: 0 0 1px #2196F3;
    }

    input:checked + .slider:before {
        -webkit-transform: translateX(26px);
        -ms-transform: translateX(26px);
        transform: translateX(26px);
    }
</style>
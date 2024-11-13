<template>
  <div>
    <div
      class="progress"
      role="progressbar"
      aria-label="Success example"
      aria-valuenow="progress"
      aria-valuemin="0"
      aria-valuemax="100"
      style="height: 50px"
    >
      <div
        class="progress-bar"
        :class="[progressCss]"
        :style="{
          width: `${progress}%`,
          transition: `width ${stepDuration}ms ease`,
        }"
      >
        {{ progress }}%
      </div>
    </div>
    <button @click="start()" class="btn btn-dark mt-2">START</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timerId: null,
      progress: 0,
      stepDuration: 50,
    }
  },
  computed: {
    progressCss() {
      return this.progress >= 21
        ? this.progress >= 51
          ? 'bg-danger'
          : 'bg-warning text-dark'
        : 'bg-dark'
    },
  },
  methods: {
    start() {
      this.progress = 0
      clearInterval(this.timerId)
      this.timerId = setInterval(() => {
        if (this.progress === 100) {
          clearInterval(this.timerId)
        } else {
          this.progress++
        }
      }, this.stepDuration)
    },
  },
}
</script>

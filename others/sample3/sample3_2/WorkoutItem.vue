<template>
  <li class="workout workout--running" @click="moveToWorkout">
    <h2 class="workout__title">{{ workout.description }}</h2>
    <div class="workout__details">
      <span class="workout__icon">{{
        workout.type === "running" ? "🏃‍♂️" : "🚴‍♀️"
      }}</span>
      <span class="workout__value">{{ workout.distance }}</span>
      <span class="workout__unit">km</span>
    </div>
    <div class="workout__details">
      <span class="workout__icon">⏱</span>
      <span class="workout__value">{{ workout.duration }}</span>
      <span class="workout__unit">min</span>
    </div>
  </li>
</template>

<script>
export default {
  props: ["workout"],
  methods: {
    moveToWorkout() {
      this.$emit("moveToPopup", this.workout);
    },
  },
};
</script>

<style scoped>
.workout {
  cursor: pointer;
}
</style>

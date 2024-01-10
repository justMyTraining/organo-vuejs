<template>
  <section class="vc-bg" :style="{ backgroundColor: team.secondaryColor }">
    <div class="container">
      <div class="position-relative">
        <h3 class="vc-card-title pb-3 m-0">{{ team.team }}</h3>
        <span class="vc-title-line" :style="{ backgroundColor: team.primaryColor }"></span>
      </div>
      <ul class="vc-card-container list-unstyled d-flex justify-content-center gap-4">
        <slot></slot>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    team: Object
  }
}

</script>

<style scoped>
.vc-bg {
  padding: 35px 0 40px;
  background: var(--primaryColor);
}

.vc-card-title {
  color: #212121;
  font-family: Prata, sans-serif;
  font-size: 32px;
  font-weight: 400;
  position: relative;
  text-align: center;
}

.vc-title-line {
  bottom: 0;
  display: block;
  height: 4px;
  left: 50%;
  position: absolute;
  transform: translateX(-50%);
  width: 32px;

  /* background-color: {{team.primaryColor}}; */
}

.vc-card-container {
  margin-top: 38px;
}
</style>
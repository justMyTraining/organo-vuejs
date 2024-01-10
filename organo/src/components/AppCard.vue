<template>
  <li class="vc-card" :style="{ backgroundImage: `linear-gradient(to bottom, ${cardColor} 90px, white 90px)` }">
    <img class="vc-avatar mb-3" :src="collaborator.avatar" alt="avatar">
    <p class="vc-name mb-2">{{ collaborator.name }}</p>
    <p class="vc-occupation m-0">{{ collaborator.occupation }}</p>
  </li>
</template>

<script>
export default {
  props: {
    collaborator: Object,
    cardColor: String
  }
}
</script>

<style scoped>
.vc-card {
  align-items: center;
  background-image: linear-gradient(to bottom, #57C278 90px, white 90px);
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  max-width: 262px;
  padding: 40px 32px 27px;
  width: 100%;
}

.vc-avatar {
  border-radius: 100%;
  max-width: 120px;
  width: 100%;
}

.vc-name {
  color: #6278F7;
  font-family: Montserrat, sans-serif;
  font-size: 18px;
  font-weight: 600;
  text-align: center;
}

.vc-occupation {
  color: #212121;
  font-family: Montserrat, sans-serif;
  font-size: 16px;
  font-weight: 400;
  text-align: center;
}
</style>

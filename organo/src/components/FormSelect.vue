<template>
  <div>
    <label class="vc-label d-block mb-2" for="">Time</label>
    <select class="vc-select" v-model="selectValue" name="nome" id="id">
      <option selected disabled :value="null">Selecione uma das opções</option>
      <option v-for="team in teams" :key="team" :value="team">{{ team }}</option>
    </select>
  </div>
</template>
<script>
export default {
  data() {
    return {
      selectValue: null
    }
  },
  methods: {
    clearValue() {
      this.selectValue = null;
    },
    getValue() {
      return this.selectValue;
    }
  },
  props: {
    teams: Array
  }
}
</script>
<style>
.vc-label {
  color: #212121;
  font-size: 18px;
  font-weight: 600;
}

.vc-select {
  background: #FFF;
  border: none;
  box-shadow: 10px 10px 30px 0px rgba(0, 0, 0, 0.06);
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  outline: none;
  padding: 30px 21px;
  width: 100%;
}
</style>
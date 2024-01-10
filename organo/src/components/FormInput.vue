<template>
  <div>
    <label class="vc-label d-block mb-2" :for="id">{{ label }}</label>
    <input :id="id" class="vc-input" v-model="inputValue" :name="id" :placeholder="placeholder" type="text">
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: ''
    }
  },
  methods: {
    clearValue() {
      this.inputValue = null;
    },
    getValue() {
      return this.inputValue;
    }

  },
  props: {
    id: String,
    label: String,
    placeholder: String,
  },
}
</script>
<style scoped>
.vc-label {
  color: #212121;
  font-size: 18px;
  font-weight: 600;
}

.vc-input {
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
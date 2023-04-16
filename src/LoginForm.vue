<template>
  <div>
    <label>Zaloguj się swoim e-mailem!</label>
    <input type="email" v-model="email" placeholder="Wpisz swojego e-maila">
    <button @click="enter()">Zaloguj się</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  },

  props: {
    hungry: Boolean,
    name: String,
  }
}

</script>

<style scoped>

</style>
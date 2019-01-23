<template>
  <div>
    <h1>{{ user.name }}</h1>
    <p>
      {{ user.id}} who is {{ user.age }}
      <span v-if="parseInt(user.age) < 20">madre mia</span>
    </p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
    <p>you have {{ catLength }} categories</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  computed: {
    catLength() {
      return this.$store.getters.catLength
    },
    ...mapState(['user', 'categories'])
  }
}
</script>

<style scoped>
</style>

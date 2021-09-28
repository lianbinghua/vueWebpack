<template>
  <div class="App">
    <div>
      <router-link to="/Home">go Home</router-link>
      <router-link to="/About">go About</router-link>
    </div>
    <div>
      <p>{{getCounter}}</p>
      <button @click="add">add</button>
    </div>
    <div>
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'App',
  data() {
    return {}
  },
  created() {
    this.testArr()
  },
  computed: {
    ...mapGetters(['getCounter'])
  },

  methods: {
    ...mapActions(['add']),
    testArr() {
      var arr = [1, 2, 3]
      let b = Array.from(arr, x => x + x)
      console.log(b)
    }
  }
}
</script>

<style lang="scss" scoped>
@import './assets/styles/var.scss';
.App {
  text-align: center;
  color: $primary-color;
  font-size: 28px;
}
</style>
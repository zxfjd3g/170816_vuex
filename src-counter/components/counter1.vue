<template>
  <div>
    ----clicked: {{count}} times, count is {{evenOrOdd}}
    <button @click="increment">increment</button>
    <button @click="decrement">decrement</button>
    <button @click="incrementIfOdd">increment if odd</button>
    <button @click="incrementAsync">increment async</button>
  </div>
</template>

<script>
  export default {

    mounted () {
      console.log('mounted()', this.$store)
    },

    computed: {
      count () {
        return this.$store.state.count
      },
      evenOrOdd () {
        return this.$store.getters.evenOrOdd
      }
    },

    methods: {
      increment () {
        this.$store.dispatch('increment')
      },

      decrement () {
        this.$store.dispatch('decrement')
      },

      incrementIfOdd () {
        this.$store.dispatch('incrementIfOdd')
      },

      incrementAsync () {
        this.$store.dispatch('incrementAsync')
      }
    }

  }
</script>

<style>

</style>
<template>
  <global-component></global-component>
  <local-component :title="title" @addclick="count += $event">
    <!-- Slot Teste  -->
    <template v-slot:header>
      Header
    </template>
    <template v-slot:content>
      Content
    </template>
  </local-component>
  <p>Count: {{count}}</p>
</template>

<script>
import LocalComponent from './components/LocalComponent.vue'

export default {
  data() {
    return {
      title: "Component Title",
      count: 0
    }
  },
  computed: {
    computedTitle() {
      return "Teste" + this.title
    }
  },
  methods: {

  },
  components: {
    LocalComponent
  },

  // Ganchos de inicialização
  beforeCreate() {
    console.log("before create", this.title, this.computedTitle)
  },
  created() {
    console.log('created', this.title, this.computedTitle)
  },

  // Ganchos de montagem (Inserção no DOM)
  beforeMount() {
    console.log('before mount')
  },
  mounted() {
    console.log('mounted')
  },

  // Ganchos de Atualização
  beforeUpdate() {
    console.log('Before Update')
  },
  updated() {
    console.log('Updated')
  },

  // Ganchos de destruição
  beforeUnmount() {
    console.log("Before Unmount")
  },
  unmounted() {
    console.log("Unmounted")
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

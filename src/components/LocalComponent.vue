<template>
    <h1>Local Component</h1>
    <slot name="header"></slot>
    <h2>{{title}}</h2>
    <!-- <button @click="$emit('addclick')">Add</button> -->
    <button @click="$emit('addclick', 1)">Add</button>
    <button @click="addTwo">Add Two</button>
    <br>
    <!-- <slot></slot> -->
    <slot name="content"></slot>
</template>

<script>
export default {
  props: {
      title: String // Number, Object, Boolean, Array, Function e etc
  },
  methods: {
      addTwo: function () {
          this.$emit('addclick', 2)
      }
  }
}
</script>

<style scoped>

</style>
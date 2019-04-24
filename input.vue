<template>
  <div class="form-group">
    <h3 
      v-if="!editable" 
      @click="editable = true">
      {{title}}
    </h3>
    <input 
      v-else 
      type="text" 
      :value="title" 
      @input="changeTitle" 
      @keyup.enter="editable = false">
    <input type="text">
  </div>
</template>

<script>
export default {
  props: {
    title: {
      default: '默认标题',
      type: String
    }
  },
  data () {
    return {
      editable: false
    }
  },
  methods: {
    changeTitle (e) {
      this.$emit('updata:title', e.target.value)
    }
  }
}
</script>

<style>

</style>
<template>
<div>
  <h1>header</h1>
  <editor flag="news-pub" v-model="newcon">
  </editor>
  <pre>{{newcon}}</pre>
</div>
</template>
<script>
import Vue from 'vue'

export default {
  data () {
    return { newcon: '' }
  },
  async mounted () {
    const editor = await import('~components/editor.vue')
    Vue.component('editor', editor)
    this.$forceUpdate()
  }
}
</script>

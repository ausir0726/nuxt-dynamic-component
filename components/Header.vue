<template>
<div>
  <h1>header - counter {{counter}}</h1>
  <editor v-if="!editorLoading" flag="news-pub" v-model="newcon">
  </editor>
  <div v-else>editor loading.. please wait</div>
  <pre>{{newcon}}</pre>
</div>
</template>
<script>
import Vue from 'vue'

export default {
  data () {
    return { newcon: '', editorLoading: true, counter: 0, interval: 0 }
  },
  beforeMount () {
    this.interval = setInterval(() => { this.counter += 1 }, 500)
  },
  async mounted () {
    const editor = await import('~components/editor.vue')
    Vue.component('editor', editor)
    // this.$forceUpdate()
    this.editorLoading = false // this will trigger component rerender
    clearInterval(this.interval)
  }
}
</script>

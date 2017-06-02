<template>
<div>
  <h1>header</h1>
  <editor flag="news-pub" v-model="newcon">
  </editor>
</div>
</template>
<script>
const Editor = process.BROWSER_BUILD ? require('~components/editor.vue') : ''

export default {
  components: {
    Editor
  },
  data () {
    return { newcon: '' }
  }
}
</script>

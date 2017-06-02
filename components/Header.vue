<template>
<div>
  <h1>header</h1>
  <editor flag="news-pub" v-model="newcon">
  </editor>
</div>
</template>
<script>

export default {
  data () {
    return { newcon: '' }
  }
}
</script>

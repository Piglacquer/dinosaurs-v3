<template>
  <div id="job-preview">
    <p id="message">&nbsp;</p>
    <button id="preview-toggle" @click="seen = !seen">Show Preview</button>
    <section id="application-preview" v-show='seen'>{{application}}</section>
  </div>
</template>
<script>
export default {
  name: "Preview",
  data() {
    return {
      seen: false
    }
  },
  props: {
    application: {
      type: String,
      required: true
    }
  }
}</script>
<style scoped>
</style>

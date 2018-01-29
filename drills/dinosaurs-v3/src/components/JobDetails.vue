<template>
  <section id="job-details">
    <h2>Job Details</h2>
    <h4>{{listings.title}}</h4>
    <p>{{listings.description}}</p>
  </section>
</template>
<script>
export default {
  name: "JobDetails",
  props: {
    listings: {
      type: Object,
      required: true
    }
  }
}</script>
<style scoped>
</style>

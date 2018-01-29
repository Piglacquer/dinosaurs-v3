<template>
  <div class="hello">
    <form id="application-input" v-on:submit.prevent method='POST'>
      <label>Apply Here: </label>
      <textarea id="application-text" rows="8" cols="100" v-model='application'></textarea>
      <input id="submit" type="submit" value="Submit" @click.prevent.reset="submitApp"/>
    </form>
    <p id="message">{{ message }}</p>
    <Preview v-bind:application='application'></Preview>
  </div>
</template>

<script>
import Preview from './Preview'

export default {
  name: "InputForm",
  components: {
    Preview
  },
  data() {
    return {
      application: '',
      message: ''
      }
    },
    methods: {
      submitApp(){
      this.message = 'Your application was submitted!'
    }
  }
}</script>
<style scoped>
</style>

<template>
  <div id="app">
    <Header />
    <main>
      <JobDetails v-bind:listings='listings' />
      <InputForm />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header'
import InputForm from './components/InputForm'
import JobDetails from './components/JobDetails'
import Preview from './components/Preview'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Header,
    InputForm,
    JobDetails,
    Preview,
    Footer
  },
  data(){
    return {
      apiUrl: '../../static/listing.json',
      listings: {}
    }
  },
  mounted() {
    fetch(this.apiUrl)
    .then(response => response.json())
    .then(response => this.listings = response)
    .then(response => console.log(this.listings))
  }
}</script>

<style>
html {
	margin: 0;
	padding: 0;
}

body {
	margin: 0 30px 0 30px;
	padding: 0;
	font-family: sans-serif;
	color: #1b997a;
	display: grid;
	grid-template-rows: 15% 75% 10%;
}

main {
	grid-row: 2/3;
	width: 70%;
	margin: 0 auto;
	padding: 10px;
}

main section {
	grid-column: 2/3;
}

small {
	color: black;
	font-size: 0.5rem;
	margin-left: 10px;
}

a {
	color: #c261cc;
	text-decoration: none;
}

#application-preview {
	border-radius: 6px;
	box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
	border: 1px solid darkgrey;
	min-height: 100px;
	margin-top: 20px;
	padding: 10px;
}
</style>

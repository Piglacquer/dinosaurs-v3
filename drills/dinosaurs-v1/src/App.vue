<template>
  <div id='app'>
    <Header></Header>
    <main>
      <JobList :listings="listings"></JobList>
      <JobForm :addListing="addListing"></JobForm>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header'
import JobList from './components/JobList'
import JobForm from './components/JobForm'
import Footer from './components/Footer'

export default {
  name: 'App',
  data() {
    return {
      listings: [],
      apiURL: '../static/listings.json'
    }
  },
  components: {Header, JobList, JobForm, Footer},
  mounted() {
    fetch(this.apiURL).then(response => response.json()).then(response => [this.listings = response])
  },
  methods: {
    addListing (listing) {
      this.listings.splice(0,0, listing)
    }
  }
}</script>

<style>
body {
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}

main {
  grid-row: 2/3;
  display: grid;
  grid-template-columns: 5% 42.5% 5% 42.5% 5%;
}

main section {
  grid-column: 2/3;
}

main section h2 {
  margin: 0;
  color: #61CCB1;
}
</style>

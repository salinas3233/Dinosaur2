<template>
  <div id="app">
    <Header/>
    <main>
      <section id='profiles-container'>
        <h2>Profiles</h2>
        <ul>
          <DinoProfiles v-for='(dino, index) in dinos' :key='index' :dino= 'dino'/>
        </ul>
       </section>
    </main>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import DinoProfiles from './components/DinoProfiles.vue'
import Skills from './components/Skills.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Header,
    DinoProfiles,
    Skills,
    Footer
  },
  data () {
    return {
      dinos: []
    }
  },
  mounted () {
    const URL = './dinosaurs.json'
    fetch (URL)
      .then(response => response.json())
      .then(response => {
        this.dinos = response
      })
  }
}
</script>

<style>
html {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0 30 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
main section {
      padding: 0 20px 0 20px;
      display:grid;
      margin: 0 auto;
      width: 50%;
  }
</style>

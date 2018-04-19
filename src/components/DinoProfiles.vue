<template>
   <li id= 'Profiles'>
        <header @click='toggleSkills = !toggleSkills' class='dinoCard'>
            <img :src='dino.image'>
            <h2>{{dino.name}}</h2>
        </header>
        <section class='skills-container' :class='{hidden : toggleSkills}'>
            <h4>Skills</h4>
                <Skills :skills='dino.skills'></Skills>
        </section>
   </li>
</template>

<script>
import Skills from './Skills.vue'

export default {
    name: 'Profiles',
    components: {
        Skills
    },
    props: {
        dino: {
            type: Object,
            required: true
        }
    },
    data () {
        return {
            toggleSkills: true
        }
    }
}
</script>

<style scoped>
#Profiles {
    border-radius: 6px;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
    padding: 10px;
  }
  .dinoCard {
    display: flex;
    flex-flow: row nowrap;
    /* width: 100px; */
  }
  .dinoCard img {
    width: 100px;
    height: 100px;
    border: 1px solid darkgrey;
    margin: 0 10px 0 10px;
  }
  .hidden {
    display: none;
  }
  
</style>



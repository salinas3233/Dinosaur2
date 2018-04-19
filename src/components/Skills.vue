<template>
    <!-- <div id= 'Skills'> -->
        <ul id= 'Skills'>
            <li v-for='(skill, index) in skills' :key='index'  class='skill-list'>{{skill}}</li>
        </ul>
    <!-- </div> -->
</template>

<script>
export default {
    name: 'Skills',
    props: {
        skills: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>
.skill-list {
    list-style: none;
  }
</style>



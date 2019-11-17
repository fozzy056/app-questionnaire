<template>
  <div class="questionnaire">
    <img alt="Vue logo" src="../assets/logo.png" />

    <div v-if="layout == 'Affichage1'" class="container Affichage1">
      <HelloQuestionnaire msg="Questionnaire" />
      <Login />
      <a
        class="waves-effect waves-light btn"
        v-bind:class="{ 'active': layout == 'Affichage2'}"
        v-on:click="layout = 'Affichage2'"
      >Commencer !</a>
    </div>

    <div v-if="layout == 'Affichage2'" class="container Affichage2">
      <question />
    </div>
        <br><br><br>
        <a
      class="waves-effect waves-light btn"
      v-bind:class="{ 'active': layout == 'Affichage1'}"
      v-on:click="layout = 'Affichage1'"
    >Annuler</a>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloQuestionnaire from '@/components/HelloQuestionnaire.vue'
import Login from '@/components/Login.vue'
import Question from '@/components/Question.vue'
import json from '../assets/questions.json'

export default {
  name: 'questionnaire',
  components: {
    HelloQuestionnaire,
    Login,
    Question
  },
  data () {
    return {
      layout: 'Affichage1',
      questions: json.questions
    }
  }
}
</script>

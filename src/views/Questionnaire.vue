<template>
  <div class="questionnaire">
    <!-- logo de l'appliation -- 14/10 -->
    <img alt="Vue logo" src="../assets/logo.png" />

    <!-- Premier affichage (1) et par défaut pour afficher le composant Login et le message Questionnaire + bouton commencer -- 03/11 -->
    <div v-if="layout == 'Affichage1'" class="container Affichage1">
      <HelloQuestionnaire msg="Questionnaire" />
      <!-- Affichage du composant Login -->
      <Login />
      <!-- Bouton commencer pour passer au second affichage c'est a dire le composant question -- 16/11 -->
      <a
        class="waves-effect waves-light btn"
        v-bind:class="{ 'active': layout == 'Affichage2'}"
        v-on:click="layout = 'Affichage2'"
      >Commencer !</a>
    </div>

    <!-- Second affichage (2) pour afficher le composant question 17/11 -->
    <div v-if="layout == 'Affichage2'" class="container Affichage2">
      <question />
    </div>
        <br><br><br>
    <!-- Bouton annuler pour retourner sur l'affichage 1 (Login) à tout moment 16/11 -->
        <a
      class="waves-effect waves-light btn"
      v-bind:class="{ 'active': layout == 'Affichage1'}"
      v-on:click="layout = 'Affichage1'"
    >Annuler</a>
  </div>
</template>

<script>
// @ is an alias to /src
// Importation des diffférents composants 01/11
import HelloQuestionnaire from '@/components/HelloQuestionnaire.vue'
import Login from '@/components/Login.vue'
import Question from '@/components/Question.vue'

export default {
  name: 'questionnaire',
  components: {
    HelloQuestionnaire,
    Login,
    Question
  },
  // Definition de l'affichage par défaut (1, Login) 16/11
  data () {
    return {
      layout: 'Affichage1'
    }
  }
}
</script>

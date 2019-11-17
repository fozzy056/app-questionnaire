<template>
  <div class="Question">
    <!-- ---------question 1---------- -->
    <!-- Premiere question avec definition de l'affichage, question affichée par défaut -->
    <div v-if="layout == 'Affichage1'" class="container Affichage1">
      <div class="question"><h3>Tu aimes les frites ?</h3></div>
        <p>
          <label>
            <input type="checkbox" />
            <span>Oui</span>
          </label>
        </p>
        <p>
          <label>
            <input type="checkbox" />
            <span>Non</span>
          </label>
        </p>
      <!-- Bouton pour passer à l'affichage suivant et donc question suivante -->
      <a class="waves-effect waves-light btn" v-on:click="layout = 'Affichage2'">Question 2</a>
    </div>

    <!-- ---------question 2---------- -->
    <div v-if="layout == 'Affichage2'" class="container Affichage2">
      <div class="question2"><h3>Tu aimes le chocolat ?</h3></div>
      <p>
        <label>
          <input type="checkbox" />
          <span>Oui</span>
        </label>
      </p>
      <p>
        <label>
          <input type="checkbox" />
          <span>Non</span>
        </label>
      </p>
      <a class="waves-effect waves-light btn" v-on:click="layout = 'Affichage3'">Question 3</a>
    </div>

    <!-- ---------question 3---------- -->
    <div v-if="layout == 'Affichage3'" class="container Affichage3">
      <div class="question3"><h3>Tu aimes les cailloux ?</h3></div>
      <p>
        <label>
          <input type="checkbox" />
          <span>Oui</span>
        </label>
      </p>
      <p>
        <label>
          <input type="checkbox" />
          <span>Non</span>
        </label>
      </p>
      <a class="waves-effect waves-light btn" v-on:click="layout = 'Fin'">Fin !</a>
    </div>

    <!-- ---------Fin---------- -->

    <!-- Affichage du message de fin de test et bouton pour retourner à l'accueil qui se clic tout seul... -->
    <div v-if="layout == 'Fin'" class="container Fin">
      <div class="Fin"><h2>Merci d'avoir participé à ce test !</h2></div>
      <a class="waves-effect waves-light btn" href="#/questionnaire">Retour à l'accueil !</a>
    </div>
  </div>
</template>

<script>
// Import du Json des questions
import json from '../assets/questions.json'

export default {
  name: 'Question',
  // Propriétés des champs du Json
  props: {
            numQuestion: String,
            question: String,
            attendu: String
        },

// Definition de l'affichage par défaut (question 1) et definition de la variable contenant les valeurs du Json
  data () {
    return {
      layout: 'Affichage1',
      questions: json.questions
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>

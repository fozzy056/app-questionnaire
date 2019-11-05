<template>
  <div class="questionnaire">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloQuestionnaire msg="Questionnaire"/>
    <Login />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloQuestionnaire from '@/components/HelloQuestionnaire.vue'
import Login from '@/components/Login.vue'

export default {
  name: 'questionnaire',
  components: {
    HelloQuestionnaire,
    Login
  }
}
</script>

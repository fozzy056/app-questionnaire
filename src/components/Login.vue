<template>
<div class="row">
    <form class="col s12">
      <div class="row">
        <div class="input-field col s2 offset-s4">
          <input id="first_name" type="text" class="validate">
          <label for="first_name">Prénom</label>
        </div>
        <div class="input-field col s2">
          <input id="last_name" type="text" class="validate">
          <label for="last_name">Nom</label>
        </div>
      </div>
      <div class="row">
        <div class="input-field col s4 offset-s4">
          <input id="society_name" type="text" class="validate">
          <label for="society_name">Nom de votre société</label>
        </div>
      </div>
    </form>
    <a class="waves-effect waves-light btn">Commencer !</a>
</div>
</template>

<script>
export default {
  name: 'Login'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>

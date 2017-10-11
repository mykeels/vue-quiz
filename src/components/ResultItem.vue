<template>
  <div class="item" :class="{ active: isActive }" height="600px">
    <h1 class="quiz-title">Wow you got a perfect score!</h1>
    <div class="results-ratio">You got 100% of the questions correct!</div>
    <div class="quiz-answers">
      <button class="quiz-button btn">Try again?</button>
    </div>
    <div class="results-social">
      <a href="http://twitter.com/intent/tweet?text=I%20got%203%20out%20of%203%20on%20%40urbaninstitute's%20%22How%20well%20do%20you%20know%20real%20creatures%3F%22%20quiz.%20Test%20your%20knowledge%20here%3A%20http%3A%2F%2Furbaninstitute.github.io%2Fquick-quiz%2F">
        <span class="social social-twitter follow-tw"></span>
      </a>
      <a href="https://www.facebook.com/sharer/sharer.php?u=http://urbaninstitute.github.io/quick-quiz/">
        <span class="social social-facebook follow-fb"></span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ['isActive']
}
</script>

<style>

</style>

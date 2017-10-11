<template>
  <div class="item" :class="{ active: isActive }" height="600px">
    <h1 class="quiz-title">Wow you got a perfect score!</h1>
    <div class="results-ratio">You got 100% of the questions correct!</div>
    <div class="quiz-answers">
      <button class="quiz-button btn" @click="onComplete">Try again?</button>
    </div>
    <div class="results-social">
      <a href="http://twitter.com/intent/tweet?text=tweet-result-for-survey-here">
        <span class="social social-twitter follow-tw"></span>
      </a>
      <a href="https://www.facebook.com/sharer/sharer.php?u=http://google.com">
        <span class="social social-facebook follow-fb"></span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ['isActive', 'onComplete']
}
</script>

<style>

</style>

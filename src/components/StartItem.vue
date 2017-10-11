<template>
  <div class="item" :class="{active: isActive}" height="600px">
    <h1 class="quiz-title">How well do you know real creatures?</h1>
    <div class="quiz-answers">
      <button class="quiz-button btn" @click="onComplete()">Take the quiz!</button>
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

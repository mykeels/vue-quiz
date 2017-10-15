<template>
  <div class="item" :class="{active: isActive}" height="600px">
    <h1 class="quiz-title">{{greeting.text}}</h1>
    <div class="quiz-answers">
      <button class="quiz-button btn" @click="onComplete()">{{greeting.actionText}}</button>
    </div>
  </div>
</template>

<script>

  export default {
    props: ['isActive', 'onComplete', 'greeting']
  }
</script>

<style>

</style>

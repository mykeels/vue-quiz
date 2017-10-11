<template>
  <div class="item" :class="{ active: isActive }" height="600px">
    <div class="quiz-question">{{question.title}}</div>
    <div class="quiz-answers">
      <button class="quiz-button btn" v-for="child in question.children" :key="child.title">{{child.title}}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['isActive', 'question', 'onComplete']
}
</script>

<style>

</style>

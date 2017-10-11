<template>
  <div class="item" :class="{ active: isActive }" height="600px">
    <div class="quiz-question">{{getCurrentQuestion().title}}</div>
    <div class="quiz-answers">
      <button class="quiz-button btn" v-for="child in getCurrentQuestion().children" :key="child.title"
            @click="answerQuestion(getCurrentQuestion().title, child.title, child.question)">{{child.title}}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['isActive', 'question', 'onComplete', 'onAnswer'],
  methods: {
    getCurrentQuestion() {
      return this.question
    },
    answerQuestion(title, answer, next) {
      this.onAnswer({
        title: title,
        answer: answer
      })
      if (next) {
        this.getCurrentQuestion = function () {
          return next;
        }
        console.log("next", next, this.getCurrentQuestion());
        this.$forceUpdate();
      }
      else {
        this.onComplete();
      }
    }
  }
}
</script>

<style>

</style>

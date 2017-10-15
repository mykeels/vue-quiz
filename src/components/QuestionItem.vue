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
        console.log(next);
        if (typeof next === 'string') { //get questions from json file
          this.$http.get(next).then((res) => {
            this.getCurrentQuestion = function () {
              return res.data;
            }
            this.$forceUpdate();
          })
        }
        else {
          this.getCurrentQuestion = function () {
            return next;
          }
          this.$forceUpdate();
        }
      }
      else {
        this.getCurrentQuestion = function () {
          return this.question;
        }
        this.onComplete();
      }
    }
  }
}
</script>

<style>

</style>

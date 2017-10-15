<template>
  <div class="container-fluid">
    <div id="quiz" class="carousel slide" data-ride="carousel">
      <ol class="progress-circles">
        <li class="dark"></li>
        <li class=""></li>
        <li class=""></li>
      </ol>
      <div class="carousel-inner" role="listbox">
        <StartItem :is-active="state === STATES.GREETINGS" :on-complete="itemCompleteHandler" :greeting="greeting" />
        <QuestionItem :is-active="state === STATES.QUESTIONS" :question="quiz" :on-complete="itemCompleteHandler" :on-answer="answerHandler" />
        <ResultItem :is-active="state === STATES.RESULTS" :on-complete="itemCompleteHandler" />
      </div>
    </div>
  </div>
</template>

<script>
import './App.css'
import StartItem from './components/StartItem'
import QuestionItem from './components/QuestionItem'
import ResultItem from './components/ResultItem'
import questions from '../static/questions/index.json'

export default {
  name: 'app',
  components: {
    StartItem,
    QuestionItem,
    ResultItem
  },
  methods: {
    itemCompleteHandler() {
      if (this.state === this.STATES.RESULTS) this.state = this.STATES.GREETINGS
      else this.state++;
    },
    answerHandler(info) {
      if (info) {
        this.answers.push(info);
        console.log("answer", this.answers)
      }
    }
  },
  data() {
    return questions
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<!--

  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
  -->

<template>
  <div class="container-fluid">
    <div id="quiz" class="carousel slide" data-ride="carousel">
      <ol class="progress-circles">
        <li class="dark"></li>
        <li class=""></li>
        <li class=""></li>
      </ol>
      <div class="carousel-inner" role="listbox">
        <StartItem :is-active="state === STATES.GREETINGS" />
        <QuestionItem :is-active="state === STATES.QUESTIONS" :question="quiz" />
        <ResultItem :is-active="state === STATES.RESULTS" />
      </div>
    </div>
  </div>
</template>

<script>
import './App.css'
import StartItem from './components/StartItem'
import QuestionItem from './components/QuestionItem'
import ResultItem from './components/ResultItem'

export default {
  name: 'app',
  components: {
    StartItem,
    QuestionItem,
    ResultItem
  },
  data() {
    return {
      STATES: {
        GREETINGS: 0,
        QUESTIONS: 1,
        RESULTS: 2
      },
      state: 0,
      quiz: {
        title: "Do you brush your teeth everyday?",
        children: [
          {
            title: "Yes",
            children: {
              title: "Do you use toothpaste?",
              children: [
                {
                  title: "Yes"
                },
                {
                  title: "No"
                }
              ]
            }
          },
          {
            title: "No",
            children: {
              title: "Do you know about plaque?",
              children: [
                {
                  title: "Yes"
                },
                {
                  title: "No"
                }
              ]
            }
          }
        ]
      }
    }
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

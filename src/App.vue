<template>
  <div class="container-fluid">
    <div id="quiz" class="carousel slide" data-ride="carousel">
      <ol class="progress-circles">
        <li class="dark"></li>
        <li class=""></li>
        <li class=""></li>
      </ol>
      <div class="carousel-inner" role="listbox">
        <StartItem :is-active="false" />
        <QuestionItem :is-active="true" />
        <div class="item" height="600px">
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
      </div>
    </div>
  </div>
</template>

<script>
import './App.css'
import StartItem from './components/StartItem'
import QuestionItem from './components/QuestionItem'

export default {
  name: 'app',
  components: {
    StartItem,
    QuestionItem
  },
  data() {
    return {
      questions: [{
        title: "One of the following is not like the others",
        children: [
          {
            title: "Loch Ness Monster"
          },
          {
            title: "Centaur"
          },
          {
            title: "Dinosaur"
          },
          {
            title: "Mermaid"
          }
        ]
      },
      {
        title: "Do you brush your teeth everyday?",
        children: [
          {
            title: "Yes"
          },
          {
            title: "No"
          }
        ]
      }
      ]
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

<template>
  <div id="app">
    <p>{{ count }}</p>
    <h1>{{ quiz.title }}</h1>
    <div v-for="(question, index) in quiz.questions" :key="question">
      <div v-show="index === questionIndex">
        <h2>{{ question.text }}</h2>
        <ol>
          <li v-for="response in question.responses" :key="response">
            <label>
              <input
                type="radio"
                v-bind:value="response.correct"
                v-bind:name="index"
                v-model="userResponses[index]"
              />
              {{ response.text }}
            </label>
          </li>
        </ol>
        <button v-if="questionIndex > 0" v-on:click="prev">prev</button>
        <button
          v-on:click="
            next();
            stop();
          "
        >
          next
        </button>
      </div>
    </div>
    <div v-show="questionIndex === quiz.questions.length">
      <h2>Quiz finished</h2>
      <p>Total score: {{ score() }} / {{ quiz.questions.length }}</p>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

var quiz = {
  title: "Test",
  questions: [
    {
      text: "O'zbekiston poytaxti",
      responses: [{ text: "Samarqand" }, { text: "Toshkent", correct: true }],
    },
    {
      text: "O'zbekiston pul birligi",
      responses: [{ text: "Sum", correct: true }, { text: "Dollar" }],
    },
    {
      text: "P tagi nima uchun kerak",
      responses: [
        { text: "Jadval yaratish uchun" },
        { text: "Paragraf yaratish uchun", correct: true },
      ],
    },
    {
      text: "Rasm quyish uchun ishlatiladugan teg",
      responses: [{ text: "img", correct: true }, { text: "div" }],
    },
    {
      text: "Meta teglar html ning qaysi qismida yoziladi",
      responses: [{ text: "head", correct: true }, { text: "header" }],
    },
  ],
};

export default Vue.extend({
  name: "IndexPage",
  el: "#app",
  data() {
    return {
      quiz: quiz,
      questionIndex: 0,
      userResponses: Array(quiz.questions.length).fill(false),
      count: 600,
      setInsfi: 0,
      isRunning: false,
    };
  },
  methods: {
    next: function () {
      this.questionIndex++;
    },
    prev: function () {
      this.questionIndex--;
    },
    score: function () {
      return this.userResponses.filter(function (val) {
        return val;
      }).length;
    },
    start() {
      this.isRunning = true;
      this.setInsfi = setInterval(() => {
        if (this.isRunning) {
          this.count--;
        } else this.count = this.count;
      }, 1000);
    },
    stop() {
      if (this.questionIndex === this.quiz.questions.length) {
        this.isRunning = false;
        clearInterval(this.setInsfi);
      }
    },
  },
  mounted() {
    this.start();
  },
});
</script>

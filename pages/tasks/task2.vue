<template>
  <div>
    <div id="question-section">
      <div v-for="item in questions" :key="item.question">
        <p>{{ item.question.text }}</p>
        <div v-for="answr in item.question.answers" :key="answr.answer">
          <input
            type="radio"
            id="answr.answer.id"
            value="answr.answer.value"
            v-model="picked[0]"
          />
          <label for="answr.answer.id">{{ answr.answer.label }}</label>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  data() {
    return {
      picked: [0, 0, 0, 0, 0],
      questions: [
        {
          question: {
            text: "asdg",
            answers: [
              { answer: { id: "0", value: 1, label: "fgdsgf" } },
              { answer: { id: "1", value: 2, label: "fgdsgfgf" } },
              { answer: { id: "2", value: 3, label: "fgdsgfg" } },
              { answer: { id: "3", value: 4, label: "fgasdfdsgf" } },
            ],
          },
        },
        {
          question: {
            text: "asdg",
            answers: [
              { answer: { id: "0", value: 1, label: "fgdsgf" } },
              { answer: { id: "1", value: 2, label: "fgdsgfgf" } },
              { answer: { id: "2", value: 3, label: "fgdsgfg" } },
              { answer: { id: "3", value: 4, label: "fgasdfdsgf" } },
            ],
          },
        },
        {
          question: {
            text: "asdg",
            answers: [
              { answer: { id: "0", value: 1, label: "fgdsgf" } },
              { answer: { id: "1", value: 2, label: "fgdsgfgf" } },
              { answer: { id: "2", value: 3, label: "fgdsgfg" } },
              { answer: { id: "3", value: 4, label: "fgasdfdsgf" } },
            ],
          },
        },
        {
          question: {
            text: "asdg",
            answers: [
              { answer: { id: "0", value: 1, label: "fgdsgf" } },
              { answer: { id: "1", value: 2, label: "fgdsgfgf" } },
              { answer: { id: "2", value: 3, label: "fgdsgfg" } },
              { answer: { id: "3", value: 4, label: "fgasdfdsgf" } },
            ],
          },
        },
        {
          question: {
            text: "asdg",
            answers: [
              { answer: { id: "0", value: 1, label: "fgdsgf" } },
              { answer: { id: "1", value: 2, label: "fgdsgfgf" } },
              { answer: { id: "2", value: 3, label: "fgdsgfg" } },
              { answer: { id: "3", value: 4, label: "fgasdfdsgf" } },
            ],
          },
        },
      ],
    };
  },
});
</script>

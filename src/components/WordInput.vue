<template>
  <div>
    <input v-model="newWord" placeholder="단어 입력" />
    <input v-model="newMeaning" placeholder="뜻 입력" />
    <button @click="addWord">추가</button>

    <ul>
      <li v-for="(word, index) in words" :key="index">
        {{ word.word }} - {{ word.meaning }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newWord: '',
      newMeaning: '',
      words: []
    };
  },
  methods: {
    addWord() {
      this.words.push({ word: this.newWord, meaning: this.newMeaning });
      this.newWord = '';
      this.newMeaning = '';
    }
  }
};
</script>

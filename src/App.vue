<template>
  <div id="app">
    <i-container class="container">
      <i-row>
        <i-column class="markdown-column" sm="6">
          <h1>Markdown</h1>
          <i-textarea
            class="textarea"
            v-model="text"
            placeholder="Enter markdown here"
          />
        </i-column>
        <i-column sm="6">
          <h1>Formatted Text</h1>
          <div class="preview" v-html="markdownToHtml"></div>
        </i-column>
      </i-row>
    </i-container>
  </div>
</template>

<script>
import { marked } from "marked";

export default {
  name: "App",
  components: {},
  data() {
    return {
      text: "",
    };
  },
  computed: {
    markdownToHtml() {
      return marked(this.text);
    },
  },
};
</script>

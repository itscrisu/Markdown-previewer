<template>
  <v-app>
    <v-app-bar app color="darkgrey" dark>
      <v-toolbar-title>Markdown Previewer</v-toolbar-title>
      <v-spacer></v-spacer>
      <a href="https:/twitter.com/itscrisu" target="_blank" class="mr-2">
        <v-icon large>mdi-twitter</v-icon>
      </a>
      <a href="https://www.linkedin.com/in/cristiandominguezl/">
        <v-icon large>mdi-linkedin</v-icon>
      </a>
    </v-app-bar>

    <v-main>
      <v-row class="my-5 mx-3">
        <v-col cols="6">
          <v-textarea
            outlined
            clearable
            clear-icon="mdi-close-circle"
            label="Markdown"
            value="Enter your text"
            rows="13"
            v-model="textArea"
          >
          </v-textarea>
        </v-col>
        <v-col cols="6">
        <h5>Formatted text:</h5>
          <vue-markdown :source="textArea"></vue-markdown>
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import VueMarkdown from "vue-markdown";

export default {
  name: "App",

  components: {
    VueMarkdown,
  },

  data() {
    return {
      textArea: "",
    };
  },
};
</script>

<style>
a {
  text-decoration: none;
}
a:hover {
  filter: opacity(50%);
}
</style>

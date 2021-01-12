<template>
  <div :id="divId" class="content"></div>
</template>

<script>
import React from "react"; // eslint-disable-line
import ReactDOM from "react-dom";
import IdyllDocument from "idyll-document";
import * as components from "idyll-components";
import { toRefs, onMounted } from "vue";
import axios from "axios";

export default {
  props: {
    file: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const { file } = toRefs(props);
    const divId = "idyll" + Math.floor(Math.random() * Math.floor(1000));

    onMounted(() => {
      axios
        .get(`/assets/idyll/${file.value}.idyll`)
        .then((res) => {
          let idyllMarkup = res.data;
          ReactDOM.render(
            React.createElement(
              IdyllDocument,
              { markup: idyllMarkup, components, datasets: {}},
              null
            ),
            document.getElementById(divId)
          );
        })
        .catch((err) => console.log(err));
    });

    return {
      divId,
    };
  },
};
</script>

<style src="@/assets/idyll.css">
</style>

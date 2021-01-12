<template>
  <div id="idyll"></div>
</template>

<script>
import React from 'react'; // eslint-disable-line
import ReactDOM from 'react-dom';
import IdyllDocument from 'idyll-document';
import * as components from 'idyll-components';
import {toRefs, onMounted} from 'vue';
import idyllMarkup from '../assets/idyll/hello_world.idyll';

// You must provide idyllMarkup
// and the container element (a DOM node).
export default {
  props: {
    file: {
      type: String,
      required: true
    }
  },
  setup (props) {
    const { file } = toRefs(props);
    console.log(file);

    console.log(idyllMarkup);

    onMounted( () => {
      ReactDOM.render(
        React.createElement(IdyllDocument, {markup: idyllMarkup, components, datasets: {}}, null),
        document.getElementById('idyll')
      )
    })

    return {
      idyllMarkup
    }
  }
}

</script>

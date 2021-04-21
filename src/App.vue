<template>
  <div id="app">
    <HelloWorld />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
 font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0.25rem 0;
}

h1 {
  margin: 1.5rem 0;
}

a {
  display: inline-block;
  text-decoration: none;
}

p {
  margin: 0.25rem 0;
}

::placeholder {
  /* Chrome, Firefox, Opera, Safari 10.1+ */
  color: #ddd;
  opacity: 1;
  /* Firefox */
}

:-ms-input-placeholder {
  /* Internet Explorer 10-11 */
  color: #ddd;
}

::-ms-input-placeholder {
  /* Microsoft Edge */
  color: #ddd;
}

input {
  width: 100%;
  border: 0;
  outline: none;
  padding: 1.5rem;
  font-size: 1.25rem;
}

@media only screen and (min-width: 768px) {
  input {
    font-size: 2rem;
  }
}

input:focus,
button:focus {
  outline: none;
}

</style>

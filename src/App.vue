<template>
  <div id="app">
    <h2>{{msg}}</h2>
    <div class="container">
      <div class="button" @click="testScript()">Click</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hello world from App.vue',
      csInterface: null,
    }
  },
  mounted() {
    // Assign CSInterface to the this.$root vue instance. It should work in any component as this.$root.csInterface
    this.csInterface = new CSInterface;
    this.loadJSX('test.jsx');
  },
  methods: {
    testScript() {
      // Loading a function manually:
      this.csInterface.evalScript('testScript()');
    },
    loadJSX(filename) {
      // Automatically loading an entire file, assuming it's in /src/
      this.csInterface.evalScript(`$.evalFile('${this.csInterface.getSystemPath(SystemPath.EXTENSION)}/src/${filename}')`)
    }
  },
}
</script>

<style>
:root {
  --color-selection: #46a0f5;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.button {
  cursor: pointer;
  border: 2px solid var(--color-selection);
  padding: .5rem 1rem;
  width: 5rem;
  border-radius: .25rem;
}
.button:hover {
  background-color: var(--color-selection);
  color: white;
}

</style>

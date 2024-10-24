<!-- <template>
  <div>
    <h1>Dados do fetch</h1>
  </div>
  <table class="mt-5 table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Body</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in items" :key="item.id">
        <td>{{ item.name }}</td>
        <td>{{ item.email }}</td>
        <td>{{ item.body }}</td>
      </tr>
    </tbody>
  </table>
  <button @click="fetchData">carregar dados</button>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template> -->
<!-- <script>
export default {
  name: 'MyComponent',
  props: {
    msg: String
  },
  methods: {
    async fetchData() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/comments');
        if (!response.ok) {
          throw new Error('Erro na rede');
        }
        const data = await response.json();
        console.log(data); // Exibe os dados no console
      } catch (error) {
        console.error('Erro ao buscar dados:', error);
      }
    }
  }
}
</script> -->

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

</style> -->


<template>
  <h1>nem precisa explicar</h1>
  <div class="button1-1">
    <button @click="fetchData">CARREGAR DADOS</button>
  </div>
  
  <div class="button3-3">
    <button @click="fetch_carregar">ENVIAR DADO</button>
  </div>
  <div class="button2-2">
    <button @click="fetch_feche">FECHAR DADOS</button>
  </div>
  
  <table class="mt-5 table">

    <tbody>
      <tr v-for="item in items" :key="item.id">
        <td>{{ item.name }}</td>
        <td>{{ item.email }}</td>
        <td>{{ item.body }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'MyComponent',
  props: {
    msg: String
  },
  data() {
    return {
      items: []
    };
  },
  methods: {
    // async fetch_carregar(){
    // fetch('https://jsonplaceholder.typicode.com/comments',{
    //   method:'post',
    //   body: JSON.stringify({
    //     posId:'2037',
    //     id:'234',
    //     name:'paralelepipedo',
    //     email:'paralelepipedo.gmail.com',
    //     body:'dolor veritatis ipsum accusamus quae voluptates sint voluptatum et\nharum saepe dolorem enim\nexpedita placeat qui quidem aut et et est\nminus odit qui possimus qui saepe'
    //     })
    //   })
    //   .then(response => response.json())
    //   .then(json => console.log('form data',json));
    // },
    async fetchData() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/comments');
        const data = await response.json();
        this.items = data;
        console.log(this.items);
      } catch (error) {
        console.error;
      }
    },
    fetch_feche() {
      this.items = [];
    }
  }
}
</script>
<style>
.imagem-xd {
    max-width: 130px;
    height: auto;
}

button {
  font-size: 16px;
  padding: 10px 20px;
  margin-bottom: 10px;
}
.button1-1 {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 0px;
}
.button2-2 {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 0px;
}
.button3-3{
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 0px;
}

h1 {
  display: flex;
  align-items: center;
  justify-content: center;
}

table {
  color: black;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
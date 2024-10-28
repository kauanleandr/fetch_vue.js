<template>
  <div class="button1-1">
    <button @click="fetch_carregar">ENVIAR DADO</button>
  </div>

  <div class="button1-1">
    <button @click="fetchData">CARREGAR DADOS</button>
  </div>

  <div class="button1-1">
    <button @click="fetch_feche">FECHAR DADOS</button>
  </div>
  
  <div class="tabela">

    <table class="mt-5 table">

<tbody>
  <tr v-for="item in items" :key="item.id">
    <td>{{ item.name }}</td>
    <td>{{ item.email }}</td>
    <td>{{ item.body }}</td>
  </tr>
</tbody>
</table>

  </div>
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
    async fetch_carregar() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/comments', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({
            postId: '2037',
            id: '234',
            name: 'paralelepipedo',
            email: 'paralelepipedo@gmail.com',
            body: 'dolor veritatis ipsum accusamus quae voluptates sint voluptatum et\nharum saepe dolorem enim\nexpedita placeat qui quidem aut et et est\nminus odit qui possimus qui saepe'
          })
        });
        const newItem = await response.json();
        this.items.push(newItem);
        console.log('Dados atualizados:', this.items);
      } catch (error) {
        console.error('Erro ao carregar os dados:', error);
      }
    },
    async fetchData() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/comments');
        const data = await response.json();
        this.items = data;
        console.log(this.items);
      } catch (error) {
        console.error('Erro ao buscar os dados:', error);
      }
    },


    fetch_feche() {
      this.items = [];
    }
  }
}
</script>
<style>

.tabela{

  margin-top: 20px;

}

.imagem-xd {
  display: block;
  margin: 0 auto;
  max-width: 100%;
  max-width: 200px;
  height: auto;
  text-align: center
}

button {
  font-size: 16px;
  padding: 10px 10px;
}
.button1-1 {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 30px;
}

.table td {
  border: 1px solid #ddd;
  padding: 8px;
  color: black;
}

.table {
  width: 100%;
  border-collapse: collapse;
  margin: 0 auto;
  text-align: center;
}
</style>
<template>
  <div>
    <v-btn v-for="item in ['A','B','C','D']" @click="recuperaBebidas(item)" v-bind:key="item.strDrink" >
      {{ item }}
    </v-btn>
    <Bebidas v-for="item in bebidas" :datos="item" />

   
</div>

</template>

<script>
import Bebidas from './cmpBebidas.vue';
  
  export default {
    name: 'cmpBuscador',
    data() {
      return {
        bebidas: []
      }
    },
    components: {
      Bebidas
   
    },
    methods: {
      recuperaBebidas(letra) {
        fetch('https://www.thecocktaildb.com/api/json/v1/1/search.php?f='+letra)
          .then(response => response.json())
          .then(data => this.bebidas=data.drinks)
      }
    }
  }
</script>

<template>
  <div>
    <v-btn v-for="item in ['A','B','C','D']" @click="recuperaBebidas(item)" v-bind:key="item.strDrink" >
      {{ item }}
    </v-btn>

   
</div>

</template>

<script>
  
  export default {
    data() {
      return {
        bebidas: []
      }
    },
    components: {
   
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

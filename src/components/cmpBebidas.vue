<template>
    <div>
        <v-container>
            <v-card>
                <v-card-title> Bebida: {{ datos.strDrink }} </v-card-title>
                <v-img :src=datos.strDrinkThumb height="300" width="300" contain></v-img>   

            </v-card>

        </v-container>

    </div>
</template>

<script>
export default {
    name: "cmpBebidas",
    props: {
        datos: {
            type: Object,
            required: true
        }
    },
    data() {
        return {

        }
    },

}
</script>


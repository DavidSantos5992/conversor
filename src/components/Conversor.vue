<template>
    <div class="conversor">

        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input v-model="moedaA_value" type="text" :placeholder="moedaA">
        <input @click="Converter" type="button" value="Converter">
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>
export default {

    name: "Conversor",
    props:["moedaA","moedaB"],
    data(){
        return{
            moedaA_value : "",
            moedaB_value : 0
        }
    },

    methods:{
        Converter(){
            let de_para = this.moedaA + "-" + this.moedaB

            let url = "https://economia.awesomeapi.com.br/last/"+de_para+"";

            fetch(url)
            .then(res=> {
                return res.json();
            })
            .then(json => {
                console.log(json)
              let cotacao = json[de_para]
              this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
            });
        }
    },
}
</script>

<style scoped>

</style>
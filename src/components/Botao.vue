<template>
    <div>
        <a class="waves-effect waves-light btn-small" v-on:click="realizarcalculo">Clique Aqui!!</a>
    </div>
</template>

<script>
export default {
    props: ["valorD", "valorS"],
    data(){
        return{
            valor_Digitado: 0,
        }    
    },

    methods:{
        realizarcalculo(){
            if(this.valor_Digitado == this.valor_Sorteado){
                alert("Acertou")
                return 0
            }else if(this.valor_Digitado > this.valor_Sorteado){
                alert("O Número Sorteado é MENOR do que o Número Digitado!! - " + this.valor_Sorteado)
                return 1
            }else{
                alert("O Número Sorteado é MAIOR do que o Número Digitado!! - " + this.valor_Sorteado)
                return 2
            }
        }
    }
}
</script>

<style scoped>
    #inputNumero{
        text-align: center;
    }
</style>
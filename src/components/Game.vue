<template>
  <div class="row">
    <div class="col m3 l3">
      <div class="card horizontal">
        <div class="card-stacked">
          
          <div class="card-content">
            <h5>Digite o Valor</h5>
            <hr />

            <input type="number" id="inputNumero" v-model="valor_Digitado" min="1" max="100"/>
              <a v-if="tentativas < 10 && jogo == true" class="waves-effect waves-light btn-small" id="botao" v-on:click="realizarcalculo">Clique Aqui!!</a>
              <a v-if="tentativas === 10 || jogo == false" class="waves-effect waves-light btn-small" id="botao" v-on:click="novoJogo">Novo Jogo</a>
          </div>


        </div>
      </div>
    </div>

    <div class="col m9 l9">
      <Resultado :m_ensagem = "mensagem" :n_tentativa = "tentativas"/>
    </div>
  </div>
</template>

<script>
    import Resultado from "./Resultado";

    export default {
      name: 'Game',
      components: {
        Resultado
      },

    data() {
        return {
            valor_Digitado: 0,
            tentativas: 0,
            jogo: true,
            mensagem: '...',
            valor_Sorteado: Math.floor(Math.random() * (100 - 1)) + 1
        };
    },

  methods:{
        realizarcalculo(){
            if(this.valor_Digitado == this.valor_Sorteado){
                this.mensagem = 'Você Acertou o Número Sorteado!!',
                this.jogo = false

            }else if(this.valor_Digitado > this.valor_Sorteado){
                this.mensagem = "Número Sorteado é MENOR do que o Número Digitado!!",
                this.tentativas++;
        
            }else{
                this.mensagem = "Número Sorteado é MAIOR do que o Número Digitado!!",
                this.tentativas++;
            }

            if(this.tentativas === 10){
              this.mensagem = "Você Não Conseguiu Acertar o Número Sorteado!!"
            }
        },

        novoJogo(){
          this.tentativas = 0,
          this.mensagem = '...',
          this.jogo = true
        }
    }
};
</script>

<style scoped>
#inputNumero {
  text-align: center;
}
</style>
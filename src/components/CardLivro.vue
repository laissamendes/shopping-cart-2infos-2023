<script setup>
const props = defineProps({
    livro: Object
})
const emit = defineEmits(['adicionarAoCarrinho'])

function formatarPreco(preco) {
  return 'R$ ' + preco.toFixed(2).replace('.', ',')
}
import MeuBotao from "@/components/MeuBotao.vue";
import CartPlus from 'vue-material-design-icons/CartPlus.vue'
import ShareVariant from 'vue-material-design-icons/ShareVariant.vue'
</script>

<template>
    <div class="card-livro">
        <div class="card-info-livro">
          <div class="wrap-livro">
            <img :src="props.livro.img" alt="Capa do livro" class="capa-livro" />
          </div>
          <p class="titulo-livro">{{ props.livro.title }}</p>
          <p class="autor-livro">{{ props.livro.author }}</p>
          <p class="preco-livro">{{ formatarPreco(props.livro.price) }}</p>
        </div>
        <div class="card-buttons-livros">
          <meu-botao class="secundario" @click="emit('adicionarAoCarrinho', props.livro)"> <cart-plus /></meu-botao>
          <meu-botao class="sucesso"> <share-variant /> </meu-botao>
        </div>
      </div>
</template>

<style scoped>
.card-livro {
  margin: 5px 10px;
  padding: 10px;
  background-color: rgb(129, 192, 252);
  border-radius: 10px;
  width: 180px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: white;
}

.wrap-livro {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: white;
  border-radius: 10px;
  width: 180px;
  height: 270px;
}
.capa-livro {
  width: 90%;
  max-height: 100%;
}

.card-livro p {
  margin: 0;
}

.card-livro .titulo-livro {
  font-weight: bold;
  margin-bottom: 5px;
}
</style>
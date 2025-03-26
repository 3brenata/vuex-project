<template>
  <div class="cart">
    <h2>Carrinho de Compras</h2>
    <button @click="addItemToCart">Adicionar Produto</button>
    <p>Total de itens no carrinho: {{ cartItemCount }}</p>
  </div>
</template>

<style scoped>
.cart {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100vh;
}

.cart button {
  background: transparent;
  border: 1px solid greenyellow;
  padding: 15px;
  border-radius: 10px;
  color: white;
  cursor: pointer;
  transition: 0.5s;
}

.cart button:hover{
  background: greenyellow;
  transition: 0.5s;
}
.cart .clicked {
  background: rgba(172, 255, 47, 0.55) !important;
  transition: 0.5s;
}
</style>


<script>
import { mapActions, mapGetters } from 'vuex';
export default {
  computed: {
    ...mapGetters(['cartItemCount']),
  },
  methods: {
    ...mapActions(['addToCart']),
    addItemToCart() {
      const product = { id: Date.now(), name: 'Produto Exemplo' };
      this.addToCart(product);
    },
  },
};
</script>

<template>
  <div class="product-list-one">
  <h2>Product List One</h2>
	<ul>
	<li v-for="(product, index) in saleProducts" :key="index">
		<span class="nama">{{product.nama}}</span>
		<span class="harga"> {{product.harga}}</span>
	</li>
	</ul>
	<button @click="reducePrice(4)">Reduce Price</button>
  </div>
</template>

<script>
import {mapActions} from 'vuex';
import {mapGetters} from 'vuex';
export default {
  name: 'ProductListOne',
  computed:{
  product(){
  return this.$store.state.products;
  },
  ...mapGetters([
  'saleProducts',
  ])
  // saleProducts(){
  // return this.$store.getters.saleProducts;
  // }
  },
  methods:{
  ...mapActions([
  'reducePrice',
  ])
  // reducePrice(amount){
  // this.$store.state.products.forEach(product => {
  // product.harga -= 1;
  // });
  // return this.$store.commit('reducePrice');
  // return this.$store.dispatch('reducePrice', amount);
  // }
  }
}
</script>
<style scoped>
.product-list-one{
    background: #FFF8B1;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    margin-bottom: 30px;
    padding: 10px 20px;
}
.product-list-one ul{
    padding: 0;
}
.product-list-one li{
    display: inline-block;
    margin-right: 10px;
    margin-top: 10px;
    padding: 20px;
    background: rgba(255,255,255,0.7);
}
.harga{
    font-weight: bold;
    color: #E8800C;
}
</style>
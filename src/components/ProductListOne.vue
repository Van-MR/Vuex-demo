<template>
  <div id="ProductListOne">
    <h1>This is ProductListOne</h1>
    <ul>
       <li v-for="product in saleProducts">
          <span class="name">{{product.name}}</span>
          <span class="price">${{product.price}}</span>
       </li>
    </ul>
    <button @click="reducePrice(4)">商品降价</button>
  </div>
</template>

<script>
import {mapGetters} from 'vuex'
import {mapActions} from 'vuex'
export default {
  computed: {
    products (){
        return this.$store.state.products;
    },
   ...mapGetters([
     'saleProducts'
   ])
 },
 methods: {
   /*
     reducePrice:function(amount){
      this.$store.state.products.forEach(product =>{
           product.price -= 1;
      })     
     //commit触发mutation
     //this.$store.commit('reducePrice');
     //dispatch触发action
     this.$store.dispatch('reducePrice',amount);
   } 
  */ 
  //辅助函数...mapActions ...mapGetters
  ...mapActions([
    'reducePrice'
  ]) 
 }
} 
</script>

<style lang="scss">
      $text-color:#ed462f;
      $text-color-1:#48a2fb;
       #ProductListOne{
         background:#42925e;
         box-shadow:1px 2px 3px rgba(0,0,0,0.2);
         margin-bottom:30px;
         h1{
         color:$text-color;
         text-align:center;
         }
         ul{
            position:relative;
            top:-20px;
           li{
           display:inline-block;
           color:$text-color-1;
           margin-right:10px;
           margin-top:10px;
           padding:20px;
           background:rgba(255,255,255,0.7);
           .price{
            font-weight:bold;
            color:#ef6b30;
            display:block;
           }
           }
         }
      }
</style>

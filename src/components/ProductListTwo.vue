<template>
  <div id="ProductListTwo">
    <h1>This is ProductListTwo</h1>
    <ul>
       <li v-for="product in saleProducts">
          <span class="name">{{product.name}}</span>
          <span class="price">${{product.price}}</span>
       </li>
    </ul>
  </div>
</template>

<script>
export default {
  computed: {
    products (){
        return this.$store.state.products;
    },
    saleProducts(){
       return this.$store.getters.saleProducts;
    }
  }
}
</script>

<style lang="scss">
      $text-color:#d74c72;
      #ProductListTwo{
         background:teal;
         box-shadow:1px 2px 3px rgba(0,0,0,0.2);
         margin-bottom:30px;
         h1{
         color:$text-color;
         text-align:center;
         }
         ul{
           list-style:none;
           padding:0;
           li{
           color:$text-color;
           margin-right:10px;
           margin-top:10px;
           padding:20px;
           background:rgba(255,255,255,0.7);
           .price{
            font-weight:bold;
            color:#860CE8;
            display:block;
           }
           }
         }
      }
</style>

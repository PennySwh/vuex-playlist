<template>
  <div id="product-list-one">
    <h2>product-list-one</h2>
    <ul>
        <li v-for="product in saleProducts">
            <span class="name">
                {{product.name}}
            </span>
            <span class="price">
                ${{product.price}}
            </span>
        </li>
    </ul>
    <button @click="reducePrice">商品降价</button>
  </div>
</template>

<script>
export default {
    computed:{
        products(){
            return this.$store.state.products;
        },
        saleProducts(){
            return this.$store.getters.saleProducts;
            // var saleProducts = this.$store.state.products.map(
            //     product =>{
            //         return {
            //             name:"**"+product.name+"**",
            //             price:product.price/2
            //         }
            //     }
            // )
            // return saleProducts;
        }
    },
    methods:{
        reducePrice:function(amount){
            // this.$store.state.products.forEach(product =>{
            //     product.price -=1;
            // })
            //  this.$store.commit('reducePrice');
            this.$store.dispatch("reducePrice",amount);
        }
    }
}
</script>

<style scoped>
#product-list-one{
    background: #fff8b1;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    margin-bottom: 30px;
    padding: 10px 20px;
}
#product-list-one ul{
    padding: 0;
    list-style-type:none;
}
#product-list-one li{
    margin-right:10px;
    margin-top:10px;
    padding: 20px;
    background: rgba(255,255,255,0.7);
}
.price{
    font-weight:bold;
    color: #E8800c;
    display: block;
}
</style>

<script>
export default{
    props: {
        productItem:{
            imageUrl: String,
            productName: String,
            productDesc: String,
            productPrice: String,
        }
},
data() {
    return {
        count: 0
}
},

methods: {
    addAmt() {
      this.count++
    },
    subAmt() {
        this.count--
    }
}
//emits: ['response'],
  //created() {
   // this.addCart('response', 'hello from child')
  //},
    //data () {
        //return {

       // }
    //},
    }
</script>

<template>
    <div>
    <img :src="productItem.imageUrl" alt="product image" />
    <h3>{{productItem.productName}}</h3>
    <p>{{productItem.productDesc}}</p>
    <p>{{productItem.productPrice}}</p>
    <button @click="addCart">Add to Cart</button>
    <p>{{ count }}</p>
    <button @click="addAmt">+</button>
    <button @click="subAmt">-</button>
    </div>
</template>
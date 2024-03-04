<script>
export default{
    props: {
        productItem:{
            imageUrl: String,
            productName: String,
            productDesc: String,
            productPrice: String,
        }
}
}
</script>

<template>
    <img :src="productItem.imageUrl" alt="product image" />
    <h3>{{productItem.productName}}</h3>
    <p>{{ productItem.productDesc }}</p>
    <p>{{ productItem.productPrice }}</p>
</template>
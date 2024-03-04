<script>
import Header from './Header.vue'
import Footer from './Footer.vue'
import productItem from './productItem.vue'
export default {
    data() {
        return {
            description: "Text text text",
            copy: "This is copy. It's a string. Paragraph paragraph paragraph.",
            CartItem: [
                {
                    imageUrl: "https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_900,h_900/global/770437/01/fnd/PNA/fmt/png/Manchester-City-23/24-Men's-Authentic-Home-Jersey",
                    productName: "Manchester City soccer jersey",
                    productDesc: "Light blue soccer jersey.",
                    productPrice: "$145.00",
        
                },
                {
                    imageUrl: "https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_900,h_900/global/770604/01/fnd/PNA/fmt/png/Borussia-Dortmund-23/24-Men's-Home-Replica-Jersey",
                    productName: "Borussia Dortmund 23/24 Men's Home Replica Jersey",
                    productDesc: "Black and yellow soccer jersey",
                    productPrice: "$95.00",
                 },
                {
                    imageUrl: "https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_900,h_900/global/084082/02/fnd/PNA/fmt/png/PUMA-x-CHRISTIAN-PULISIC-Soccer-Ball",
                    productName: "PUMA x CHRISTIAN PULISIC Soccer Ball",
                    productDesc: "Teal, black and white soccer ball.",
                    productPrice: "$25.00",
                },
                {
                    imageUrl: "https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa,w_900,h_900/global/030815/06/fnd/PNA/fmt/png/ftblNXT-SPIRIT-Ankle-Shinguards",
                    productName: "ftblNXT SPIRIT Ankle Shinguards",
                    productDesc: "Black and purple shinguards.",
                    productPrice: "$15.00",
                },
            ], 
    }
},
    components: {
        Header,
        Footer,
        productItem
    }
}

</script>

<template>
    <header class="HomeHeader">
        <h1>Cart</h1>
    </header>

    <div>
        <div class="cartList">
            <productItem v-for="productItem in CartItem" :productItem="productItem" :key="productItem.productName" />
        </div>
    </div>

    
    <Footer></Footer>
</template>

<style scoped>
.backgroundWithImage {
    height: calc(-100px + 100vh);
    background-size: 100%;
    background-repeat: no-repeat;
    background-image: url(https://cdn.sanity.io/images/n5wk68wz/production/595bc21a01381bc136773f148879fe9e84779e69-5760x3240.webp);
}

.description {
    color: var(--color-heading);
    display: flex;
    flex-direction: column;
    -webkit-box-pack: center;
    justify-content: center;
    max-width: min(80%, 940px);
    height: calc(-50px + 100vh);
    margin: 0 auto; /* auto-center */ 
}
.description * {
    margin: 0;
}
</style>
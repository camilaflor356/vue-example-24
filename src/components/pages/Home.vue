<script>
import Header from '../Header.vue'
import Footer from '../Footer.vue'
import Cart from '../Cart.vue'
export default {
    data() {
        return {
            description: "Text text text",
            copy: "This is copy. It's a string. Paragraph paragraph paragraph.",
        }
    }, 
    components: {
        Header,
        Footer,
        Cart
    }
}
</script>

<template>
    <header class="HomeHeader">
        <h1>Home Page</h1>
    </header>
    <div class="backgroundWithImage">
        <div class="description">
            <p>Home</p>
            <h1>{{ description }}</h1>
        </div>
    </div>
    <div>
        {{ copy }}
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
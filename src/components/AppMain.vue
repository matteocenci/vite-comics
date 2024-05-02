<script>
export default{
    data() {
        return {
            sections: [
                {
                    product: "buy-comics-digital-comics.png",
                    title: "DIGITAL COMICS"
                },
                {
                    product: "buy-comics-merchandise.png",
                    title: "DC MERCHANDISE"
                },
                {
                    product: "buy-comics-subscriptions.png",
                    title: "SUBSCRIPTION"
                },
                {
                    product: "buy-comics-shop-locator.png",
                    title: "COMIC SHOP LOCATOR"
                },
                {
                    products: "buy-dc-power-visa.svg",
                    title: "DC POWER VISA"
                }
            ]
        }
    },
    methods: {
        getImagePath: function(img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        }
    }
};
</script>

<template>
    <main>
        <section class="content">
            <h2> __> Content goes here <-- </h2>
        </section>
        <section class="sections">
            <ul>
                <li v-for="item in sections">
                    <img :src="getImagePath(item.product)" alt="">
                    <a href="">{{ item.title }}</a>
                </li>
                
            </ul>
        </section>

    </main>

</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;

.content {
    margin-top: 2rem;
    padding: 2rem 0;
    padding-left: 10.5rem;
    background-color: black;
    color: #FFFFFF;
    font-family: sans-serif;

    @include flex(row, left, left);
}

.sections {
    background-color: #0F86F9;
    padding: 15px;
    ul {
        @include flex(row, center, center);
        margin: 0;
        list-style-type: none;

        a {
            text-decoration: none;
            color: #FFFFFF;
            font-family: sans-serif;
            margin-left: 10px;
        }

        li {
            @include flex(row, center, center)
        }
    }

    img {
        max-width: 10%;
    }
}






</style>
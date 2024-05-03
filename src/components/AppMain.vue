<script>
import { list1, list2, list3, list4 } from '../assets/data/lists-footer';


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
                    product: "buy-dc-power-visa.svg",
                    title: "DC POWER VISA"
                }
            ],
            footer: [
                {
                    title: "DC COMICS",
                    list: list1
                },
                {
                    title: "SHOP",
                    list: list2
                },
                {
                    title: "DC",
                    list: list3
                },
                {
                    title: "SITES",
                    list: list4
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

        <section class="utilities">
            <div class="info">
                <ul class="father">
                    <li v-for="menu in footer">
                        <h4>{{ menu.title }}</h4>
                        <ul>
                            <li v-for="item in menu.list"><a href="">{{ item }}</a></li>
                        </ul>
                    </li>
    
                </ul>

            </div>
            <div class="logo">

            </div>
        </section>

    </main>

</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;

.content {
    
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
        max-width: 40px;
        margin-left: 70px;
    }
}

.utilities {
    @include flex(row, left, center);
    width: 100%;
    background-image: url("../assets/img/footer-bg.jpg");
    background-repeat:no-repeat;
    
    
    
    
    .info {
        width: 50%;
        .father{
            @include flex (row, center, start);
            flex-wrap: wrap;
            padding: 70px;

            li {
                @include flex(column, left, left);
                

                h4 {
                    color: #FFFFFF
                }
                a {
                    list-style-type: none;
                    text-decoration: none;
                    color: gray;
                }

            }
        }

    }
    .logo {
        width: 50%;
        background-image: url("../assets/img/dc-logo-bg.png");
    }


}





</style>
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
            ],
            images: [
                {
                    "thumb": "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                    "price": "$19.99",
                    "series": "Action Comics",
                    "type": "comic book",
                },
                {
                    "thumb": "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                    "price": "$3.99",
                    "series": "American Vampire 1976",
                    "type": "comic book",
                },
                {
                    "thumb": "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                    "price": "$16.99",
                    "series": "Aquaman",
                    "type": "graphic novel",
                },
                {
                    "thumb": "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                    "price": "$2.99",
                    "series": "Batgirl",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                    "price": "$3.99",
                    "series": "Batman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                    "price": "$2.99",
                    "series": "Batman Beyond",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                    "price": "$3.99",
                    "series": "Batman/Superman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                    "price": "$4.99",
                    "series": "Batman/Superman Annual",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                    "price": "$5.99",
                    "series": "Batman: The Joker War Zone",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                    "price": "$6.99",
                    "series": "Batman: Three Jokers",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                    "price": "$4.99",
                    "series": "Batman: White Knight Presents: Harley Quinn",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                    "price": "$16.99",
                    "series": "Catwoman",
                    "type": "graphic novel",
                }
            ]
        }
    },
    methods: {
        getImagePath: function(img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        }
    },
};


</script>

<template>
    <main>
        
        <section class="content">
            <img src="../assets/img/jumbotron.jpg" alt="">
            <div class="comics">
                <div class="card">
                    
                </div>

            </div>
            
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
                <img src="../assets/img/dc-logo-bg.png" alt="">

            </div>
        </section>

    </main>

</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;



.content {
    
    
    
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
    
    background-image: url("../assets/img/footer-bg.jpg");
    
    
    background-repeat:i;
    
    
    
    
    .info {
        width: 50%;
        .father{
            @include flex (row, center, start);
            flex-wrap: wrap;
            padding: 70px;

            li {
                @include flex(column, left, left);
                margin: 0 20px;
                width: 100px;
                
                
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

    .logo img{
        width: 80%;
    }
    
    


}





</style>
<script>
export default {
    data() {
        return {
            menu: [
                {
                    title: "CHARACTERS",
                    isActive: false
                },
                {
                    title: "COMICS",
                    isActive: true
                },
                {
                    title: "MOVIES",
                    isActive: false
                },
                {
                    title: "TV",
                    isActive: false
                },
                {
                    title: "GAMES",
                    isActive: false
                },
                {
                    title: "COLLECTIBLES",
                    isActive: false
                },
                {
                    title: "VIDEOS",
                    isActive: false
                },
                {
                    title: "FANS",
                    isActive: false
                },
                {
                    title: "NEWS",
                    isActive: false
                },
                {
                    title: "SHOP",
                    isActive: false
                },
                

            ]

        }
    }
}
</script>




<template>
    <header>
        <div class="header-logo">
            <img src="../assets/img/dc-logo.png" alt="Logo DC">
        </div>
        <ul class="navigation">
            <li v-for="item in menu">
                <a href="" :class="{ active: item.isActive}">{{ item.title }}</a>
            </li>
            
            
        </ul>

    </header>

</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

header {
    @include flex(row, space-between, center);
    .header-logo {
        text-align: left;
        margin: 20px
    }

    ul {
        @include flex(row, right, right);
        list-style-type: none;
        gap: 1rem;
        margin: 0 10px;
        padding: 0 20px;
        li {
            
            
            a {
                padding: 10px 16px;
                text-decoration: none;
                color: black;
                display: inline-block;
                font-size: 14px;
                font-family:Verdana, Geneva, Tahoma, sans-serif;
                font-weight: 600;
    
                
                
                
                &:hover {
                    color: #0F86F9;
                }
    
                &.active {
                    border-bottom: 5px solid #0F86F9;
                    color: #0F86F9;
                    
                }
    
            }

        }

    }
}

</style>
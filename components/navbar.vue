<template>
    <div class="wrapperNav">
        <div class="wrapperNaw_logo">
            <NuxtLink :to="'/'"><img src="https://ippevg.github.io/PhServer/Assets/LogoTM.png" class="wrapperNaw_logo_image" alt="Logo"></NuxtLink>
        </div>    
        <ul>
            <li v-for="(item,index) in li" :key="index">
                <NuxtLink :to="item.to">{{ item.label }}</NuxtLink>           
            </li>
        </ul>
        <div class="checkInBlock">
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="https://ippevg.github.io/PhServer/Assets/iconsHeart.png" class="checkInBlock_items_item" alt="heart">
                </NuxtLink>
            </div>
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="https://ippevg.github.io/PhServer/Assets/iconsBag.png" class="checkInBlock_items_item" alt="bag">
                </NuxtLink>
            </div>
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="https://ippevg.github.io/PhServer/Assets/iconsBurgerMenu.png" class="checkInBlock_items_item" alt="burger">
                </NuxtLink>
            </div>
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue'
    export default {
        setup() {
            const li = ref (
                [{ label: 'Home', to: '/' },
                { label: 'About Us', to: '/about' },
                { label: 'Contacts', to: '/contacts' }]
            )
            return{
                li
            }
        }
    }
</script>

<style scoped lang="scss">
.wrapperNav{
    display: grid;
    grid-template-rows: 80px;
    grid-template-columns: 1fr 9fr 3fr;
    margin: 30px auto ;
    max-height: 80px;
    .wrapperNaw_logo{
        max-width: 100%;

    }
}
.checkInBlock{
    max-width: max-content;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 4%;
    height: 100%;
    .checkInBlock_items{
        max-width: 10%;
        .checkInBlock_items_item{
            width: 100%;
            padding: 10%;
            box-sizing: border-box;
        }
    }
}
ul{
    display: flex;
    flex-direction: row;
    align-items:center;
    justify-content: end;
    list-style: none;
    padding: 0;
    li{
        padding: 20px;
        gap: 20px;
    }
}

</style>
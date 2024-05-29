<template>
    <div class="wrapperNav">
        <div class="wrapperNaw_logo">
            <NuxtLink :to="'/'"><img src="../assets/imges/LogoTM.png" class="wrapperNaw_logo_image" alt="Logo"></NuxtLink>
        </div>    
        <ul>
            <li v-for="(item,index) in li" :key="index">
                <NuxtLink :to="item.to">{{ item.label }}</NuxtLink>           
            </li>
        </ul>
        <div class="checkInBlock">
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="../assets/imges/iconsHeart.png" class="checkInBlock_items_item" alt="heart">
                </NuxtLink>
            </div>
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="../assets/imges/iconsBag.png" class="checkInBlock_items_item" alt="bag">
                </NuxtLink>
            </div>
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <img src="../assets/imges/iconsBurgerMenu.png" class="checkInBlock_items_item" alt="burger">
                </NuxtLink>
            </div>
            <div class="checkInBlock_items">
                <NuxtLink :to="'#'">
                    <p class="checkInBlock_items_item__p">Вход</p>
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
                [{ label: 'Главная', to: '/' },
                { label: 'Скидки', to: '/about' },
                { label: 'Контакты', to: '/contacts' }]
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
    grid-template-columns: 2.5fr 9fr 5fr;
    margin: 20px auto ;
    max-height: 80px;
    .wrapperNaw_logo{
        max-width:100%;
        min-width: 120px;
        display: flex;
        align-items: center;
        justify-content: center;
        img{
            width:100%;

        }
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
    padding: 0 20px;
    .checkInBlock_items{
        max-width: 100%;
        .checkInBlock_items_item{
            max-width: 50px;
            padding: 15px;
            box-sizing: border-box;
        }
        .checkInBlock_items_item__p{
            padding: 0 15px;
        }
        
    }
}

ul{
    display: flex;
    flex-direction: row;
    align-items:center;
    justify-content: end;
    list-style: none;
    margin-right: 20px;
    padding: 0;
    li{
        padding: 20px;
        gap: 20px;
    }
}


</style>
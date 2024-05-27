<template>
    <div class="wrapperNav">
        <NuxtLink>logo</NuxtLink>
        <ul>
            <li v-for="(item,index) in li" :key="index">
                <NuxtLink :to="item.to">{{ item.label }}</NuxtLink>           
            </li>
        </ul>
        <div class="CheckInBlock">
            
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
    display: flex;
    justify-content: space-between;
    align-items: center;
}
ul{
    display: flex;
    flex-direction: row;
    align-items:center;
    justify-content: end;
    list-style: none;
    padding: 0;
    li{
        padding: 10px;
        gap: 20px;
    }
}

</style>
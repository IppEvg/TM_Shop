<script>
import { reactive,onMounted } from 'vue';

export default {
    setup() {
        let list = reactive([])
        const loadList = async ()=>{
            try {
                const loading = await fetch("https://ippevg.github.io/PhServer/List.json")
                if (loading.ok) {
                const data = await loading.json()
                console.log(...data.posts);
                list.push(...data.posts)
                } else {
                console.error("Ошибка при загрузке данных:", response.status)
                }
            } catch (error) {
                console.error("Ошибка сети или сервера:", error)
            }
        }
    onMounted(loadList)
    return{onMounted,list}
    },
}
</script>


<template>
    <div class="main_pictures">
        <img src="../assets/imges/Obl1.jpg" alt="left" class="main_pictures__item">
        <img src="../assets/imges/Obl2.jpg" alt="lright" class="main_pictures__item">
    </div>
    <ul class="listContainer">
    <li v-for="(item) in list" :key="item.id">
        <div class="listContainer_image">
            <img :src="item.jpg" alt="jpg">
        </div>
        <h3>
          {{ item.title }}
        </h3>
    </li>
  </ul>
</template>

<style scoped lang="scss">
.listContainer{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
    max-width: 2000px;
    list-style: none;
    li{
        padding: 5px;
        h3{
            text-align: center;
        }
    }
    .listContainer_image{
        max-width: 300px;
        max-height: 450px;
        img{
            width: 100%;
            height:325px;
        }
    }
}

</style>
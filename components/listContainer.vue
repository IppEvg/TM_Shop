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
    <div class="listContainer_filters">


    </div>
    <div>
        <aside>
            
        </aside>
        <ul class="listContainer">
            <li v-for="(item) in list" :key="item.id">
                <a href="#" class="listContainer_item">
                    <div class="listContainer_image">
                        <img :src="item.jpg" alt="jpg">
                    </div>
                    <h3 class="listContainer_title">
                        {{ item.title }}
                    </h3>
                    <p class="listContainer_articule listContainer_item__gray">
                            Артикул: {{ item.articule }}
                    </p>
                    <p class="listContainer_color listContainer_item__gray">
                            Цвет: {{ item.color }}
                    </p>
                    <p class="listContainer_cost">
                            {{ item.cost }} p.
                    </p>
                    <div class="listContainer_size listContainer_item__gray">
                            Размер
                        <select name="" id="size" class="listContainer_option" >{{ item.size[0] }}
                        <option v-for="(size,idx) in item.size" :key="idx" class="listContainer_color" >{{ size }}</option>
                    </select>
                    </div>
                </a>
                <button class="listContainer_button">
                        В корзину
                </button>
            </li>
        </ul>
    </div>
</template>

<style scoped lang="scss">
.listContainer{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    list-style: none;
    font-size: 10px;
    gap: 10px;
    margin-top: 10px;
    
    li,a{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        padding: 5px;
        // background-color: rgba(173, 171, 171, 0.514);
    }
    &_image{
        max-width: 150px;
        max-height: 450px;
        img{
            width: 100%;
            height: 187px;
        }
    }
    &_button{
       @include button-standart;
       width:90%;
    }
    &_button:hover{
        opacity: 0.95;
        transform: scale(1.02);
    }
    &_cost{
        font-size: 14px;
    }
    &_item__gray{
        color:#313030c2;
        margin:2px;

    }
    &_option{
        border-radius:4px;
    }
}
</style>
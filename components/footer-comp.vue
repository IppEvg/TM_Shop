<script>
export default{

}
</script>

<template>
    <div class="table_menu">
        <div class="table_menu_item">
            <img src="../assets/imges/LogoTM.png" alt="Logo">
            <a href="#" class="gif-block"><img src="../assets/imges/telegram.svg"  alt="TG"></a>
            <div>	&copy; 2024 TooMuch</div>
        </div>
        <div class="table_menu_item">
            <h4>Компания</h4>
            <a href="#">Главная</a>
            <a href="#">О нас</a>
            <a href="#">Контакты</a>
        </div>
        <div class="table_menu_item">
            <h4>Покупателям</h4>
            <a href="#">Оплата</a>
            <a href="#">Доставка</a>
            <a href="#">Написать нам</a>
        </div>
        <div class="table_menu_item">
            <h4>Документы</h4>
            <a href="#">Политика</a>
            <a href="#">Оферта</a>
            <a href="#">Обмен и возврат</a>
        </div>
    </div>
    <div class="bottom">
        <h6>Разработка сайта:ippevg@yandex.ru</h6>
    </div>  
</template>

<style scoped lang="scss">
.table_menu{
    background-color: rgba(201, 201, 201, 0.404);
    display: grid;
    padding:10px 0px 20px;
    margin-top: 20px;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    &_item{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 2px;
        img{
            max-width: 90px;
            .gif-block{
                width: 20px;
            }
        }
        h4{
            margin:0.8em 0;
        }
    }
}
.bottom{
    background-color:rgba(133, 132, 132, 0.555); 
    h6{
        margin: 0;
        padding: 10px 0px 30px;
        text-align: center;
        
    }
}
</style>
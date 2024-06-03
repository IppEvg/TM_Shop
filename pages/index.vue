<script>
import listContainer from '~/components/listContainer.vue';
import footerComp from '~/components/footer-comp.vue';

</script>


<template>
    <div class="main_wrapper">
        <div class="main_pictures">
            <img src="../assets/imges/Obl1.jpg" alt="left" class="main_pictures__item">
            <img src="../assets/imges/Obl2.jpg" alt="lright" class="main_pictures__item">
        </div>
        <h1>Каталог</h1>
        <listContainer></listContainer>
    </div>
    <footerComp></footerComp>
    
</template>

<style scoped lang="scss">
.main_wrapper{
    margin: 0 auto;
    h1{
        max-width:800px;
        margin: 10px auto;
        font-size: 45px;
    }
}
.main_pictures{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    &__item{
        max-width: 300px;
        max-height: 300px;
        box-shadow: 0px 0px 10px 4px rgba(0,0,0,0.75);
    }
}


</style>
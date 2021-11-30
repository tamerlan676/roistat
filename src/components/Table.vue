<template>
    <div>
        <div class="table head">
            <div class="item">Имя</div>
            <div class="item">Номер телефона</div>
        </div>
        <div class="table" v-for="(item, index) in table" :key="index">
            <div class="item">{{ item.name }}</div>
            <div class="item">{{ item.phone }}</div>
        </div>
    </div>
    
</template>
<script>

export default ({
    props: [ 'table' ],

})
</script>


<style scoped>
    .table{
        display: flex;
        width: 800px;
        margin: auto;
    }

    .head .item{
        font-weight: bold;
    }
    .item{
        width: 50%;
        border: 1px solid #e5e5e5;
        padding: 10px;
        text-align: left;
        box-sizing: border-box;
    }
</style>
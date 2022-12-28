<template>

    <div class="table">
        <img class="table_img" :src="imgUrl" alt="#">
        <div class="table_name">{{ title }}</div>
        <div class="table_price">{{ price }}руб.</div>
        <p class="table_remains">Доступно только {{ count }}шт.</p>
        <button class="btn" @click="addToBasket" type="button">Добавить в корзину</button>
    </div>
</template>

<script>
export default {
    name: 'ProductCard',

    props: {
        title: String,
        price: Number,
        imgUrl: {
            type: String,
            default: 'https://otdelkaonline.ru/foto/415841-1.jpg',
        },
        count: {
            type: Number,
        },
    },
    data() {
        return {

        }
    },
    methods: {
        addToBasket() {
            this.$emit('addToBasket')
        }
    }
}
</script>

<style lang="scss" scoped>
.table {
    margin-right: 20px;
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 400px;
    border: 2px solid #ccc;
    padding: 20px;
    border-radius: 2px;
}

.table_img {
    width: 100%;
    height: 100%;
    margin-bottom: 10px;
}

.table_name {
    font-weight: 700;
    font-size: 20px;

    margin-bottom: 5px;
}

.table_price {
    font-weight: 600;
}

.table_remains {
    color: rgb(146, 146, 146);
}

.btn {
    width: 50%;
}
</style>

<template>

    <h1>Письменные Столы</h1>
    <my-input />
    <input type="search" v-model="searchText" />
    <button class="btn">Найти</button>
    <!-- <input type="search" :value="searchText" @input="$event.target.value" /> -->
    <ul class="list_default">
        <li v-for="(product, index) in products" :key="index">
            <product-card :title="product.title" :price="product.price" :imgUrl="product.imgUrl" :count="product.count"
                @addToBasket="addToBasket(index)" />

        </li>
    </ul>

</template>

<script>

import ProductCard from './ProductCard';
import MyInput from './MyInput';

export default {
    name: 'Product_list',
    components: {
        ProductCard,
        MyInput,
    },

    data() {
        return {
            searchText: '',
            products: [
                {
                    title: 'Стол jim',
                    price: 1999,
                    imgUrl: 'https://royally.ru/Files/pt/picture/0318/50_1521032551.jpg',
                    count: 30,
                }, {
                    title: 'Стол monaco',
                    price: 1999,
                    imgUrl: 'https://royally.ru/Files/pt/picture/0318/50_1521032551.jpg',
                    count: 28,
                }, {
                    title: 'Стол нормальный такойsssssssssssssssssssssssssssssssssssssssssssss',
                    price: 1999,
                    imgUrl: 'https://royally.ru/Files/pt/picture/0318/50_1521032551.jpg',
                    count: 12,
                }
            ]

        }
    },
    methods: {
        addToBasket(index) {
            console.log(index);
        }
    }
}




</script>

<style lang="scss">
.list_default {
    display: flex;
    flex-wrap: wrap;
}
</style>
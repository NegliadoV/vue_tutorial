<template >
    <div lass="search">

        <h1>Я найду тебя</h1>
        <input type="search" v-model="search">
        <div>{{ `Всего имен ${persons.length} Cовпадений: ${searchHeandler.length}` }}</div>

        <ul>
            <li v-for="item in searchHeandler" :key="item">
                <p>{{ item.name }}</p>
            </li>

        </ul>
    </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            search: '',
            persons: [
                { name: 'Анна' },
                { name: 'Витплий' },
                { name: 'Евгений' },
                { name: 'Сергей' },
                { name: 'Владимир' },
                { name: 'Кристина' },
                { name: 'Маша' },
                { name: 'Таня' },
                { name: 'Лев' },
                { name: 'Генадий' },

            ]
        }
    },
    computed: {
        searchHeandler() {
            return this.persons.filter(el => {
                return el.name.toLowerCase().includes(this.search);
            })
        }
    }
}
</script>

<style>
.search {
    display: flex;
    flex-direction: column;
}
</style>
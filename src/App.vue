<template>
    <div class="app" id="app">
        <!-- <search /> -->
        <!-- <my-component /> -->
        <!-- <ShawarmaCat /> -->
        <product-list />

    </div>

</template>
   
<script>
import ProductCard from './components/ProductCard';
import ProductList from './components/ProductList';


// import ShawarmaCat from './components/ShawarmaCat';
// import Search from './components/Search';
// import MyComponent from "./components/MyComponent"

export default {
    name: "App",
    components: {
        // MyComponent,
        // Search,
        // ShawarmaCat,
        ProductList,
        ProductCard,


    }
};
</script>
  

<style>
.app {

    display: block;
    box-sizing: border-box;
    margin: 0 auto;
}
</style>

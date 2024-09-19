<template>
  <div id="app">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
      href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap"
      rel="stylesheet">
    <div class="container">
      <SidebarMenu />
      <div class="content">
        <Header :productName="productName" :productQuantity="productQuantity" :user="user" />
        <SearchBar />
        <div class="product-list">
          <ProductCard v-for="(car, index) in cars" :key="index" :car="car" />
        </div>
        <Pagination :displayed="this.cars.length" :total="totalProducts" />
      </div>
    </div>
  </div>
</template>

<script>
import SidebarMenu from './components/Sidebar.vue';
import Header from './components/Header.vue';
import SearchBar from './components/Bar.vue';
import ProductCard from './components/ProductCard.vue';
import Pagination from './components/Pagination.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    SidebarMenu,
    Header,
    SearchBar,
    ProductCard,
    Pagination,
  },
  data() {
    return {
      productName: 'Vechicles',
      user: {
        name: 'Jonh Doe',
        avatar: 'https://via.placeholder.com/40',
      },
      cars: [],
    };
  },
  computed: {
    productQuantity() {
      return this.cars.length;
    },
    totalProducts() {
      return this.cars.length;
    },
  },
  methods: {
    async getCars() {
      try {
        const response = await axios.get('https://api.caiman-app.de/api/cars-test?search=2323&per_page=9&page=1');
        this.cars = response.data.data;
        // console.log(this.cars);
      } catch (error) {
        console.error("Ошибка при получении данных:", error);
      }
    }
  },
  mounted() {
    this.getCars();
  },
};
</script>

<style>
.container {
  display: flex;
  font-family: "DM Sans", sans-serif;
  font-style: normal;
}

.content {
  flex-grow: 1;
}

.product-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: 15px;
}
</style>

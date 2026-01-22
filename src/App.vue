<!-- eslint-disable @typescript-eslint/no-unused-expressions -->
<script>
import axios from 'axios';
import categaryComponent from './components/categaryComponent.vue';
import posterComponent from './components/posterComponent.vue';
import navigationBar from './components/navigationBar.vue';
import product from './components/productComponent.vue';
export default {
    components: {posterComponent, categaryComponent, navigationBar, product},
    
  data() {
      return {
        promotions: [],
        categories: [],
        products: []
      }
  },

  methods: {
    async fetchPromotions() {
      try {
        const response = await axios.get('http://localhost:3000/api/promotions');
        this.promotions = response.data;
        console.log(this.promotions);
      } catch (error) {
        console.error(error);
      }
    },


    async fetchCategories(){
      try {
        const response = await axios.get('http://localhost:3000/api/categories');
        this.categories = response.data;
        console.log(response.data);
      } catch (error) {
        console.log(error)
      }
    },

    async fetchProducts(){
      try {
        const response = await axios.get('http://localhost:3000/api/products');
        this.products = response.data;
        console.log(response.data);
      } catch (error) {
        console.log(error)
      }
    }

  },

  mounted() {
    this.fetchPromotions();
    this.fetchCategories();
  }
}

</script>

<template>
    <navigationBar title="Featured Categories"></navigationBar>
    <div>
        <div class="categary-container">
            <categaryComponent 
                v-for="category in categories" 
                :key="category.id"
                :color="category.color" 
                :image="`http://localhost:3000/${category.image}`" 
                :text="category.name" 
                :quantity="category.productCount">
            </categaryComponent>
        </div>
        <div class="poster-container">
            <posterComponent
              v-for="promo in promotions"
              :key="promo.id"
              :image="`http://localhost:3000/${promo.image}`"
              :title="promo.title"
              :buttonColor="promo.buttonColor"
            ></posterComponent>
        </div>
    </div>
    <br>
    <br>
    <br>
    <br><br>
    <navigationBar title="Popular Products"></navigationBar>
    <div class="categary-container">
        <product 
          v-for="prod in products" 
          :key="prod.id"
          :name="prod.name" 
          :rating="prod.rating" 
          :size="prod.size" 
          :image="prod.image" 
          :price="prod.price" 
          :promotionAsPercentage="prod.promotionAsPercentage" 
          :categoryId="prod.categoryId" 
          :inStock="prod.inStock" 
          :countSold="prod.countSold" 
          :group="prod.group">
        </product>
      </div>
</template>

<style scoped>

.categary-container {
    width: 100%;
    display: flex;
    justify-content: space-between;
} 
.poster-container {
    width: 100%;
    display: flex; 
    justify-content: center;
    gap: 60px;
    margin-top: 30px;
    height: 200px;
}
.product-container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

</style>


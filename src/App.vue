<script>
import categaryComponent from './components/categaryComponent.vue';
import posterComponent from './components/posterComponent.vue';
import cat4 from './assets/img/cat-4.png';
import cat5 from './assets/img/cat-5.png';
import cat6 from './assets/img/cat-6.png';
import cat7 from './assets/img/cat-7.png';
import cat8 from './assets/img/cat-8.png';
import cat9 from './assets/img/cat-9.png';
import cat10 from './assets/img/cat-10.png';
import cat11 from './assets/img/cat-11.png';
import cat12 from './assets/img/cat-12.png';
import cat13 from './assets/img/cat-13.png';
import Cms1 from './assets/img/Cms-1.png';
import Cms2 from './assets/img/Cms-2.jpg';
import Cms3 from './assets/img/Cms-3.png';
export default {
    components: {posterComponent, categaryComponent},
    data() {
        return {
            cat4,
            cat5,
            cat6,
            cat7,
            cat8,
            cat9,
            cat10,
            cat11,
            cat12,
            cat13,
            Cms1,
            Cms2,
            Cms3
        }
    }
}

</script>

<template>
    <div>
        <div class="categary-container">
            <categaryComponent color="Red" :image="cat4" text="apple" :quantity="68"></categaryComponent>
            <categaryComponent color="yellow" :image="cat5" text="Snacks" :quantity="34"></categaryComponent>
            <categaryComponent color="black" :image="cat6" text="Black plums" :quantity="25"></categaryComponent>
            <categaryComponent color="green" :image="cat7" text="Vegetable" :quantity="65"></categaryComponent>
            <categaryComponent color="yellow" :image="cat8" text="Headphone" :quantity="33"></categaryComponent>
            <categaryComponent color="orange" :image="cat9" text="Cake & milk" :quantity="54"></categaryComponent>
            <categaryComponent color="orange" :image="cat10" text="Orange" :quantity="63"></categaryComponent>
            <categaryComponent color="blue" :image="cat11" text="Peach" :quantity="17"></categaryComponent>
            <categaryComponent color="lightgreen" :image="cat12" text="Organic Kiwi" :quantity="21"></categaryComponent>
            <categaryComponent color="lightyellow" :image="cat13" text="Cake & Milk" :quantity="14"></categaryComponent>
        </div>
        <div class="poster-container">
            <posterComponent backgroundColor="lightblue" :image="Cms1" title="Everyday Fresh & Clean with Our Products" ><buttonComponent>Shop Now &#8594;</buttonComponent></posterComponent>
            <posterComponent backgroundColor="lightpink" :image="Cms2" title="Make your Breakfast Healthy and Easy" ><buttonComponent>Shop Now &#8594;</buttonComponent></posterComponent>
            <posterComponent backgroundColor="lightpink" :image="Cms3" title="The best Organic Products Online" buttonColor="orange"><buttonComponent>Shop Now &#8594;</buttonComponent></posterComponent>
        </div>
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
    gap: 20px;
    margin-top: 30px;
    height: 200px;
}

</style>


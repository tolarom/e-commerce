<template>
    <div :style="{ border: '1px solid ' + color }" class="category">
        <img v-if="image" :src="image" alt="category image" class="category-image"/>
        <p class="item">{{ text }}</p>
        <p class="quantity">{{ quantity }} items</p>
    </div>
</template>

<script>
    export default {
        props: {
            color: {
                type: String,
                default: 'Green'
            },
            image: {
                type: String,
                default: ''
            },
            text: {
                type: String,
                default: 'Category'
            },
            quantity: {
                type: Number,
                default: 0
            }
        }
    }
</script>
 
<style scoped>
.category {
    width: 136px;
    height: 177px;
    border-radius: 10px;
    background-color: rgba(195, 189, 189, 0.493);
    margin: 15px;
    cursor: pointer;
}
.category-image {
    width: 90px;
    height: auto;
    margin: 15px;
    align-items: center;
}
.item {
    font-size: 18px;
    font-weight: 600;
    text-align: center;
    color: rgb(54, 51, 51);
}
.quantity {
    font-size: 12px;
    text-align: center;
    font-weight: 50;
    color: rgba(128, 128, 128, 0.621);
}
</style>
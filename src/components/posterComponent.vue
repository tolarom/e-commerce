<template>
    <div class="poster" :style="{backgroundColor: backgroundColor}">
        <img v-if="image" :src="image" alt="poster image" class="poster-image"/>
        <p class="title">{{ title }}</p>
        <button :style="{backgroundColor: buttonColor}" class="poster-button">
            <slot></slot>
        </button>
    </div>
</template>

<script>
    export default {
        props: {
            image: String,
            title: String,
            backgroundColor: {
                type: String,
                default: 'lightgray'
            },
            buttonColor: {
                type: String,
                default: 'green'
            }


        }
    }
</script>

<style scoped>
.poster {
    position: relative;
    width: 512px;
    height: 300px;
    border-radius: 10px;
}
.poster-image {
    width: 100%;
    height: 100%;
    border-radius: 10px;
    object-fit: cover;
}
.title {
    width: 40%;
  position: absolute;
  top: 35%;
  left: 30%;
  transform: translate(-50%, -50%);
  color: rgb(47, 47, 47);
  font-size: 20px;
  font-weight: bold;
}
.poster-button {
  position: absolute;
  top: 70%;
  left: 20%;
  transform: translate(-50%, -50%);
  padding: 10px 20px;
  color: rgb(255, 255, 255);
  border: 0px;
  cursor: pointer;
  font-size: 18px;
  border-radius: 5px;
}
</style>
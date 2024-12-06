<template>
  <li>
    <img src="https://cdn-icons-png.flaticon.com/512/1308/1308491.png" />
    <hr/>
    <slot name="card-hearder"></slot>
    <slot name="card-button"></slot>
    <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {
    name:"CARD"
}
</script>

<style scoped>
    li{
        margin: 1rem 0;
        font-size: 1.25rem;
        font-weight: bold;
        background: rgb(80, 255, 159);
        padding: 0.5rem;
        color: #0a0a0a;
        border-radius: 25px;
    }
    img{
        width: 100px;
        height: 100px;
    }
</style>
<template>
    <Card>
        <template v-slot:card-header>
            <h1>{{ name }}</h1>
        </template>
        <template v-slot:card-button>
            <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
            <button @click="deleteEmployee(id)">ลบข้อมูล</button>
        </template>
        <template v-slot:card-content>
            <transition name="fade">
            <div v-show="isVisible">
                <p>เงินเดือน: {{ salary }} บาท , ตำแหน่งงาน: {{ department }}</p>
            </div>
            </transition>
        </template>
    </Card>
</template>
  
<script>
import Card from './Card.vue';

export default {
    name:"PErson",
    components:{
        Card
    },
    props:{
        id:{
            type:Number
        },
        name:{
            type:String,
            Required:true
        },
        salary:{
            type:Number,
            default:15000
        },
        department:{
            type:String,
            Required:true
        },
        isVisible:{
            type:Boolean
        }
    },
    methods:{
        showDescription(id){
            this.$emit("showdatadetail", id);
        },
        deleteEmployee(id){
            this.$emit("delete", id)
        }
    }
}
</script>

<style scoped>
    button{
        font: inherit;
        cursor: pointer;
        border: 1px solid rgb(233, 255, 31);
        background: rgb(223, 255, 31);
        color: black;
        padding: 0.05rem 1rem;
        box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
    }

    .fade-enter-from{
        opacity: 0;
    }
    .fade-enter-active{
        transition: all 0.5s linear;
    }
</style>
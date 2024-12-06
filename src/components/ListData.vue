<template>
    <ul>
        <Person 
        v-for="item in employees" 
        :id="item.id"
        :key="item.id" :name="item.name" :salary="item.salary"
        :department="item.department"
        :isVisible="item.isVisible"
        @showdatadetail="toggleVisible"
        @delete="removeEmployee"/>
    </ul>
</template>

<script>
import Person from './Person.vue';

export default {
    name:"ListData",
    components:{
        Person,
    },
    data(){
        return{
            employees:[
                { id:1, name:"ohm", salary:30000, department:"โปรแกรมเมอร์",isVisible:false },
                { id:2, name:"Killua", salary:40000 , department:"ภารโรง",isVisible:false },
                { id:3, name:"Luffy", salary:50000 , department:"การตลาด",isVisible:false },
                { id:4, name:"Zoro", salary:60000 , department:"โปรแกรมเมอร์",isVisible:false },
                { id:5, name:"Kon", salary:70000 , department:"แม่บ้าน",isVisible:false },
            ]
        }
    },
    methods:{
        toggleVisible(id){
            this.employees= this.employees.map((item)=>{
                if(item.id === id){
                    return {...item,isVisible: !item.isVisible}
                }
                return item
            })
        },
        removeEmployee(id){
            this.employees = this.employees.filter(item=>{
                return item.id !== id
            })
        }
    }
}
</script>

<style scoped>
    ul{
        list-style: none;
        margin: 1rem 0;
        padding: 0;
    }
</style>
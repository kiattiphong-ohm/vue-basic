<template>
  <form action="">
    <div class="form-control">
        <label for="emp-name">ชื่อพนักงาน</label>
        <input type="text" v-model="employee.name">
    </div>
    <div class="form-control">
        <label for="salary">เงินเดือน</label>
        <input type="number" v-model="employee.salary">
    </div>
    <div class="form-control">
        <label for="department">ตำแหน่งงาน</label>
        <select name="" id="" v-model="employee.department">
            <option value="โปรแกรมเมอร์" selected>โปรแกรมเมอร์</option>
            <option value="การตลาด">การตลาด</option>
            <option value="ภารโรง">ภารโรง</option>
            <option value="แม่บ้าน">แม่บ้าน</option>
        </select>
    </div>
    <div class="form-control">
        <h2>เพศ</h2>
        <div>
            <input type="radio" value="ชาย" v-model="employee.gender"/>
            <label for="gender">ชาย</label>
        </div>
        <div>
            <input type="radio" value="หญิง" v-model="employee.gender"/>
            <label for="gender">หญิง</label>
        </div>
    </div>
    <div>
        <button>บันทึก</button>
    </div>
  </form>
</template>

<script>
export default {
    name:"FromComponent",
    data(){
        return{
            employee:{
                name:"",
                salary:0,
                department:"โปรแกรมเมอร์",
                gender:""
            }
        }
    }

}
</script>

<style scoped>
form{
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.25);
    padding: 2rem;
    background: #fff;
}
.form-control{
    margin: 0.5rem 0;
}
label{
    font-weight: bold;
}
input,select{
    display: block;
    width: 100%;
    font:inherit;
    margin-top: 0.5rem;
}
button{
    font: inherit;
    background: #f39428;
    color: black;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 15px;
}
input[type="radio"]{
    display: inline-block;
    width: auto;
    margin-right: 1rem;
}
input[type="radio"]+label{
    font-weight: normal;
}
h2{
    font-size: 1rem;
    margin: 0.5rem 0;
}
</style>
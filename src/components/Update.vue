<template>
    <Header />
    <h1>สวัสดี {{ fullname }} </h1>
    <h2>คุณอยู่ในหน้าแก้ไขข้อมูลในระบบ</h2>

    <div class="signup">
        <input type="text" placeholder="ชื่อร้าน" v-model="foodshops.sname">
        <input type="text" placeholder="เบอร์ติดต่อ" v-model="foodshops.contact">
        <input type="password" placeholder="ที่อยู่" v-model="foodshops.address">

        <button @click="updateFoodShop">ปรับปรุงข้อมูล</button>
    </div>
    
</template>

<script>
    import Header from './Header.vue'
    // import axios from 'axios'

    export default{
        name: 'UpdatePage',
        data(){
            return{
                fullname: '',
                foodshops: {
                    sname: '',
                    contact: '',
                    address: ''
                }
            }
        },

        components: {
            Header,
        },

        methods:{
            updateFoodShop(){}
        },

        mounted(){
            let user = localStorage.getItem("user-data")
            this.fullname = JSON.parse(user).fullname
            if(!user){
                this.$router.push({
                    name: 'SignIn' //เปลี่ยนไปหน้าเข้าสู่ระบบ
                })
            }
        }
        
    }

</script>

<style>


</style>
<template>
    <Header />
    <h1>สวัสดี {{ fullname }} </h1>
    <h2>คุณอยู่ในหน้าเพิ่มข้อมูล</h2>

</template>

<script>
    import Header from './Header.vue'

    export default{
        name: 'AddPage',
        components: {
            Header,
        },

        data(){
            return{
                fullname: ''
            }
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
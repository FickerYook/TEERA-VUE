<template>
    <Header />
    <h1>สวัสดี {{ fullname }} </h1>
    <h2>ยินดีต้อนรับเข้าสู่ระบบ</h2>
    <table>
        <tr>
            <th>ID</th>
            <th>NAME</th>
            <th>CONTACT</th>
            <th>ADDRESS</th>
        </tr>

        <tr v-for="fs in foodshops" :key="fs.id">
            <td>{{ fs.id }}</td>
            <td>{{ fs.name }}</td>
            <td>{{ fs.contact }}</td>
            <td>{{ fs.address }}</td>
        </tr>
    </table>

</template>

<script>
    import Header from './Header.vue'
    import axios from 'axios'

    export default{
        name: 'HomePage',
        data(){
            return{
                fullname: '',
                foodshops: [],
            }
        },

        components: {
            Header,

        },

        async mounted(){
            document.title = "IT06"
            let user = localStorage.getItem("user-data")
            this.fullname = JSON.parse(user).fullname 

            let result = await axios.get("http://192.168.10.20:3000/foodshops");
                // console.warn(result);
                this.foodshops = result.data

            if(!user){
                this.$router.push({
                    name: 'SignIn' //เปลี่ยนไปหน้าเข้าสู่ระบบ
                });
            }

            
            
        },                   
    }

</script>

<style>
table{
    width: 95%;
}
 .fs{
    margin: auto;
    display: block;

 }

th{
    border: 1px solid gray;
}
td{
    border: 1px solid orange;
}

</style>
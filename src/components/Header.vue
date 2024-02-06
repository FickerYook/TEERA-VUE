<template>
    <div class="menu">
        <router-link to="/">หน้าแรก</router-link>
        <router-link to="/add">เพิ่มข้อมูล</router-link>
        <router-link to="/update">ปรับปรุงข้อมูล</router-link>
        <a href="" @click="signout">ออกจากระะบบ</a>
    </div>
</template>

<script>
export default {
    name: 'HeaderMenu',
    methods: {
        signout() {
            console.log("ออกจากระะบบ");
            localStorage.clear();
            this.$router.push({ name: 'SignIn' });
        }
    }
}


</script>

<style>
* {
    margin: 0;
    padding: 0;
}

.menu {
    background-color: rgb(243, 152, 4);
    overflow: hidden;
    

}

.menu a {
    color: white;
    font-size: 20px;
    text-decoration: none;
    float: left;
    margin: 10px 15px;
    box-sizing: border-box;
    padding: 5px;
}

.menu a:hover {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}

.menu a:focus {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}

.menu router-link a:focus {
    border-bottom: 2px solid rgb(47, 31, 2);
    padding: 0;
}</style>
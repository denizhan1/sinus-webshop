<template>
<div id="app" class="Nav">
    <nav>
    
        <div class="nav-bar">
            <img src="~@/assets/sinus-logo.svg">
            <div class="right-side">
                <router-link style="text-decoration:none;" class="products" to="/Products">Products</router-link>
                <router-link style="text-decoration:none;" class="register" to="/">Register</router-link>
                <button  class="profile-btn"><img class="profile-img" src="~@/assets/icon-user-black.svg"></button>
            </div> 
            <Cart />
            </div>
    </nav>
   
 </div>
</template>

<script>
import Cart from './Cart.vue'

export default {
  components: { Cart },
    name: 'Nav',
    
}

</script>

<style lang="scss" scoped>

nav {
    position: relative;
    
}

img {
    height: 100px;
    width: 100px;
}
.nav-bar {
    margin-left: 10px;
    display: flex;
    justify-content: space-between;
}
.right-side {
    height: 50px;
    :visited{
        color: black;
    }
    :link{
        color: black;
    }
    :hover{
        color: darkgrey;
        border-bottom-color: #ff5858;
    }
    
    display: flex;
    justify-content: flex-end;
    text-decoration-line: none;
    margin: 10px;
}
.profile-btn{
    margin-left: 10px;
    margin-top: 20px;
    display: flex;
    align-items: center;
    justify-items: center;
    border-radius: 100px;
    background-color: lightgray;
    border: none;
    width: 30px;
    height: 30px;
    cursor:pointer;
    .profile-img{
        width: 20px;
        height: 20px;
        margin-left: auto;
        margin-right: auto;
    }
    
}

.products{
    margin-left: 15px;
    margin-top: 26px;
    
}
.register{
    margin-left: 15px;
    margin-top: 26px;
}


</style> 
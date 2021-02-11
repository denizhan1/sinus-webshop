<template>

<div id="app">
  
 
  <nav class="nav">
    <div class="nav__cart">
        <div class="cart-icon-border">
       
        </div>
      <button @click="showCart = !showCart">
          <span class="total-quantity">{{ totalQuantity }}</span>
          <div  class="badge" :class="{ animate: animate }" v-if="cart.length > 0">> <img class="cart-icon" src="~@/assets/icon-bag-white.svg" alt=""></div>
        <i class="fas fa-shopping-cart"></i>
      </button>
      
      <div v-if="showCart" class="cart-dropdown">
          <p v-if="!cart.length">No items in cart.</p>
          <article class="cart-item" v-for="(item, index) in cart" :key="index" @click="removeFromCart(index)">
        </article>
        <ul class="cart-dropdown__list">
          <li
            v-for="product in cart"
            :key="product.id"
          >
          <p>Price</p>
            {{ product.name }} ({{ product.quantity }})
            <footer>Total:</footer>
          </li>
        </ul>
      </div>
    </div>
  </nav>

 
  <section class="products">
    <div v-for="product in products" :key="product.id" class="product">
      <h3 class="product__header">{{ product.name }}</h3>
      <img
        src="~@/assets/hoodie-fire.png"
        :alt="product.name"
        class="product__image"
      >
      <p class="product__description">{{ product.description }}</p>
      <div class="cart">
        <button
          @click="updateCart(product, 'subtract')"
          class="cart__button"
        >
          -
        </button>
        <span class="cart__quantity">{{ product.quantity }}</span>
        <button
          @click="updateCart(product, 'add')"
          class="cart__button"
        >
          +
        </button>
      </div>
    </div>
  </section>  
  
</div>

</template>

<script>

export default {
    name: "Cart",
    
    el: '#app',
  
  data() {
    return {
        showCart: false,
        animate: false,
        products: [
        {
          id: 1,
          name: 'Product 1',
          description: 'This is an incredibly awesome product',
          quantity: 0,
        },
        {
          id: 2,
          name: 'Product 2',
          description: 'This is an incredibly awesome product',
          quantity: 0,
        },
        {
          id: 3,
          name: 'Product 3',
          description: 'This is an incredibly awesome product',
          quantity: 0,
        }
      ],
      //showCart: false
    };
  },
  
  computed: {
    cart() {
      return this.products.filter(product => product.quantity > 0);
    },
    totalQuantity() {
      return this.products.reduce(
        (total, product) => total + product.quantity,
        0
      );
    }
  },
    watch: {
        cart(){
            this.animate = true;
            
            setTimeout(() => {
                this.animate = false;
            }, 400)
        }
    },
    methods: {
      updateCart(product, updateType) {      
        for (let i = 0; i < this.products.length; i++) {
          if (this.products[i].id === product.id) {
            if (updateType === 'subtract') {
              if (this.products[i].quantity !== 0) {
                this.products[i].quantity--;
              }
            } else {
              this.products[i].quantity++;
            }
            
            break;
          }
        }
      }
    },
  }
  
  

</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
  font-weight: normal;
  margin: 0;
  padding: 0;
}

html {
  font-size: 10px;
}

.cart-icon{
    width: 20px;
    height: 20px;
    margin-right: 5px;
    cursor: pointer;
}
.nav {
  align-items: center;
  color: white;
  display: flex;
  justify-content: flex-end;
  padding: 2rem;
  
  &__header {
    font-size: 2.5rem;
  }
  
  &__cart {
    position: relative;
    
    button {
      background: none;
      border: 0;
      color: white;
      cursor: pointer;
    }
    
    i {
      font-size: 2rem;
    }
    
    .total-quantity {
      align-items: center;
      background: lightblue;
      border-radius: 50%;
      display: flex;
      font-weight: bold;
      height: 1rem;
      justify-content: center;
      padding: 0.7rem;
      position: absolute;
      //right: -10px;
      //top: -10px;
      width: 1rem;
      margin-left: 3rem;
      margin-bottom: 2rem;
    }
    
    .cart-dropdown {
      margin-left: 20px;
      margin-top: 25px;
      background: white;
      border: 1px solid lightgray;
      border-radius: 10px;
      box-shadow: 0 0 2px rgba(0, 0, 0, 0.2);
      color: #333;
      font-size: 1.3rem;
      overflow: auto;
      padding: 0 1rem;
      position: absolute;
      width: 20rem;
      .cart-dropdown__list {
        list-style: none;
        
        li {
          margin: 1rem 0;
        }
      }
    }
  }
}

.products {
    margin-top: 10rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  
  .product {
    border: 1px solid lightgray;
    border-radius: 10px;
    margin: 2rem;
    padding: 1rem;
    
    &__header {
      font-size: 2rem;
      text-align: center;
    }
    
    &__image {
      display: block;
      margin: 1rem auto;
    }
    
    &__description {
      font-size: 1.3rem;
      margin-top: 1rem;
    }
  }
}

.cart {
  margin-top: 2rem;
  text-align: center;
  
  &__button {
    background: lightblue;
    border: 0;
    color: white;
    cursor: pointer;
    font-size: 1.5rem;
    font-weight: bold;
    height: 2.5rem;
    width: 2.5rem;
  }
  
  &__quantity {
    font-size: 1.5rem;
    margin: 0 1rem;
  }
}
.badge {
            width: 30px;
            height: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
            background: salmon;
            font-size: .7rem;
            font-weight: 700;
            border-radius: 999rem;
            position: absolute;
           // transform: translate3d(1rem, -1rem, 0);
           // box-shadow: 0 0 1rem rgba(0,0,0,.2);

           /* &.animate {
                animation: drop .5s ease forwards;

                @keyframes drop {
                    from { transform: translate3d(1rem, -1rem, 0) scale(2); opacity: 0; }
                      to { transform: translate3d(1rem, -1rem, 0) scale(1); opacity: 1; }
                }
            }*/
        }

</style>
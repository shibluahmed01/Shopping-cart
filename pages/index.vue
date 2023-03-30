<template>
  <div class="container">
    <div class="flex">
      <div v-for="(product, i) in products" :key="i">
        <div class="box">
          <div class="product">
            <div >
              <img :src="product.image" alt="" />
            </div>
            <div>
              <p>
                {{ product.id }}
              </p>
            </div>
            <div class="top">
              <p>
                {{ product.title }}
              </p>
            </div>
            <div>
              <p>
                $
                {{ product.price }}
              </p>
            </div>
            <div>
              <p>
                {{ product.category }}
              </p>
            </div>
            <!-- <div>
              <p>
                {{ product.description }}
              </p> -->
            </div>
            <br>
            <div class="down">
              <p class="read">Read More</p>
              <p class="cart" @click="cartStore.add(product.id)">
                Add to Cart
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Items from "../store/data";


export default {
  data() {
    return {
      products: Items,
      
    };
  },
};
</script>

<style scoped>
.flex {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  margin: 1rem;
}
/* .pic {
  width: 300px;
  height: 300px;
} */

.product {
  width: 300px;
  height: 600px;
  font-family: Arial,  sans-serif;
}

.container {
  max-width: 1400px !important;
  margin: auto;
}

.down{
  display: flex;
  justify-content: space-between;
  
}

.read{
  background: blue;
  border-radius: 5px;
  color: white;
  padding: 0.5rem;
}

.read:hover{

background: rgb(39, 98, 207);
}

.cart{
  background: blue;
  
  border-radius: 5px;
  color: white;
  padding: 0.5rem;
}

.cart:hover{
  background: rgb(39, 98, 207);
}

.top{
  font-weight: bold;
 
}
</style>

<template>
  <div class="container">
    <div class="flex">
      <div v-for="(product, i) in products" :key="i">
        <div class="box">
          <div class="product">
            <div class="pic">
              <img :src="product.image" alt="" />
            </div>
            <div>
              <p>
                {{ product.id }}
              </p>
            </div>
            <div>
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
            <div>
              <button color="primary">Read More</button>
              <button class="bg-primary" @click="cartStore.add(product.id)">
                Add to Cart
              </button>
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
.pic {
  width: 100%;
  height: 470px;
}

.product {
  width: 300px;
}

.container {
  max-width: 1400px !important;
  margin: auto;
}
</style>

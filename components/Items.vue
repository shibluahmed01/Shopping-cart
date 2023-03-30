<template>
  <div class="cart-page">
    <h1>Your Cart</h1>
    <div v-if="items.length">
      <table>
        <thead>
          <tr>
            <th>Product Name</th>
            <th>Price</th>
            <th>Quantity</th>
            <th>Subtotal</th>
            <th></th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in items" :key="index">
            <td>{{ item.name }}</td>
            <td>{{ item.price }}</td>
            <td>
              <input
                type="number"
                v-model="item.quantity"
                @change="updateItem(index)"
                min="1"
              />
            </td>
            <td>{{ item.price * item.quantity }}</td>
            <td>
              <button @click="removeItem(index)">Remove</button>
            </td>
          </tr>
        </tbody>
      </table>
      <p>Total: {{ total }}</p>
      <button @click="checkout">Checkout</button>
    </div>
    <div v-else>
      <p>Your cart is empty</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, name: "Product A", price: 10, quantity: 1 },
        { id: 2, name: "Product B", price: 20, quantity: 1 },
      ],
    };
  },
  computed: {
    total() {
      return this.items.reduce(
        (acc, item) => acc + item.price * item.quantity,
        0
      );
    },
  },
  methods: {
    updateItem(index) {
      if (this.items[index].quantity < 1) {
        this.items[index].quantity = 1;
      }
    },
    removeItem(index) {
      this.items.splice(index, 1);
    },
    checkout() {
      // TODO: implement checkout logic
    },
  },
};
</script>

<style>
table {
  border-collapse: collapse;
  width: 100%;
}

th,
td {
  text-align: left;
  padding: 8px;
  border-bottom: 1px solid #ddd;
}

th {
  background-color: #f2f2f2;
}

button {
  background-color: #4caf50;
  border: none;
  color: white;
  padding: 8px 16px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

input[type="number"] {
  width: 60px;
}
</style>

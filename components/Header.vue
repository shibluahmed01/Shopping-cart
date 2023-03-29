<template>
  <div class="navber">
    <div class="left">
      <p>Shopping Website</p>
    </div>
    <div class="right">
      <div class="picture">
        <img
          src="https://media.istockphoto.com/id/1206806317/vector/shopping-cart-icon-isolated-on-white-background.jpg?s=612x612&w=0&k=20&c=1RRQJs5NDhcB67necQn1WCpJX2YMfWZ4rYi1DFKlkNA="
          alt=""
        />
      </div>
      <div class="theme">
        <img
          src="https://thumbs.dreamstime.com/b/brightness-icon-vector-sign-symbol-isolated-white-backgro-brightness-icon-vector-isolated-white-background-your-web-133736656.jpg"
          alt=""
        />
        <p @click="toggleTheme()">ToggleTheme</p>
      </div>
    </div>
  </div>
</template>

<script></script>

<style scoped>
.navber {
  display: flex;
  justify-content: space-between;
  background: white;
  box-shadow: rgba(18, 15, 15, 0.56) 0px 1px 0px 4px;
}

.right {
  display: flex;
}

.left {
  font-size: 30px;
  font-weight: bold;
}

.theme {
  display: flex;
  font-size: 30px;
  font-weight: bold;
}

.theme img {
  width: 30px;
  width: 25px;
}

.picture {
  width: 40px;
  height: 30px;
  margin-right: 1rem;
}
</style>

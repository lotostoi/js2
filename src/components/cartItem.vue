<template>
  <div class="show_basket" id="basket_item">
    <div class="cart_basket_img">
      <img :src="cartItem.productImg" alt="" class="img_basket" />
      <div class="text_img_basket">
        <p>
          {{ cartItem.productName }} <br />
          <span>{{ cartItem.quantity }} x {{ cartItem.productPrice }}</span>
        </p>
        <p>
          <i class="far fa-star star_color"></i>
          <i class="far fa-star star_color"></i>
          <i class="far fa-star star_color"></i>
          <i class="far fa-star star_color"></i>
          <i class="far fa-star star_color"></i>
        </p>
        <a
          href="#"
          class="fas fa-times-circle"
          @click.prevent="decItem(cartItem)"
          name="remov"
          data-id="cartItem.productId"
        ></a>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  props: ['cart-item'],
  methods: {
    ...mapActions({
      addItem: 'cart/incCart',
      decItem: 'cart/decCart',
    }),
  },
}
</script>

<style></style>

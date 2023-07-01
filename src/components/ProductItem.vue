<template>
  <div class="card text-left mt-3">
    <img class="card-img-top" :src="productItem.image" alt="">
    <div class="card-body">
      <h4 class="card-title">{{ productItem.name }}</h4>
      <p class="card-text text-danger font-weight-bold">{{ productItem.price }} VND</p>
    </div>
    <div class="mb-2">
        <button class="btn btn-danger ml-2"
         @click="handleBuy(productItem)">
            Mua
        </button>
        <button class="btn btn-info ml-2" @click="handleOpenModalDetail">
            Chi Tiết
        </button>
    </div>
  </div>
  <teleport to="#app">
    <app-modal :isOpen="isOpenModalDetail"
                :handleCloseModal="handleCloseModalDetail">
      <product-detail :productDetail="productItem"></product-detail>
    </app-modal>
  </teleport>
</template>

<script>
import ProductDetail from './ProductDetail.vue'
export default {
  components: {
    ProductDetail
  },
  data() {
    return {
      isOpenModalDetail: false
    }
  },
  props: {
    productItem: {
      type: Object,
    }
  },
  methods: {
    handleBuy(productItem) {
      this.$emit('handle-buy', productItem)
    },
    handleCloseModalDetail() {
      this.isOpenModalDetail = false;
    },
    handleOpenModalDetail() {
      this.isOpenModalDetail = true;
    },
  }
}
</script>

<style>

</style>
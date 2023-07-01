<template>
  <section class="product-list">
    <h2 class="text-center text-danger font-weight-bold mt-2">Các sản phẩm nổi bật</h2>
    <div class="pro-list row">
        <div v-for="(productItem, index) in productList" :key="index" class="col-lg-3">
            <product-item :productItem="productItem" 
                    @handle-buy="handleBuy"/>
        </div>
    </div>
  </section>
</template>

<script>
import ProductItem from './ProductItem.vue'
import sp1 from '../assets/images/sp1.png'
import sp2 from '../assets/images/sp2.png'
import sp3 from '../assets/images/sp3.png'
import sp4 from '../assets/images/sp4.png'
import sp5 from '../assets/images/sp5.png'
import sp6 from '../assets/images/sp6.png'
import sp7 from '../assets/images/sp7.png'
import sp8 from '../assets/images/sp8.png'
export default {
    methods: {
        handleBuy(productItem) {
            this.$emit('handle-buy', productItem)
        }
    },
    data() {
        return {
            productList: [
                {
                    id: 1,
                    name: "Bộ bàn phím",
                    image: sp1,
                    description: 
                    "Phím và chuột có dây dài phù hợp với nhiều loại hệ điều hành khác nhau, nhiều cấu hình máy của PC",
                    price: 134000,
                    sale: 10,
                    quantityInStock: 10,
                },{
                    id: 2,
                    name: "Chuột Captain Marvel",
                    image: sp2,
                    description: 
                    "Phím và chuột có dây dài phù hợp với nhiều loại hệ điều hành khác nhau, nhiều cấu hình máy của PC",
                    price: 250000,
                    sale: 5,
                    quantityInStock: 15,
                },{
                    id: 3,
                    name: "Laptop Gamming",
                    image: sp3,
                    description: 
                    "Phím và chuột có dây dài phù hợp với nhiều loại hệ điều hành khác nhau, nhiều cấu hình máy của PC",
                    price: 1050000,
                    sale: 0,
                    quantityInStock: 5,
                },{
                    id: 4,
                    name: "Lót chuột",
                    image: sp4,
                    description: 
                    "Lót chuột chống chày sước bàn ghế",
                    price: 230000,
                    sale: 5,
                    quantityInStock: 35,
                },{
                    id: 5,
                    name: "Tai nghe",
                    image: sp5,
                    description: 
                    "tai nghe hiện đại",
                    price: 750000,
                    sale: 5,
                    quantityInStock: 15,
                },{
                    id: 6,
                    name: "Loa Sony",
                    image: sp6,
                    description: 
                    "Nghe nhạc cực chất",
                    price: 1000000,
                    sale: 10,
                    quantityInStock: 15,
                },{
                    id: 7,
                    name: "Màn hình View Sonic",
                    image: sp7,
                    description: 
                    "Độ phân giải cực nét full HD",
                    price: 134000,
                    sale: 10,
                    quantityInStock: 10,
                },{
                    id: 8,
                    name: "Mic thu âm",
                    image: sp8,
                    description: 
                    "Khử ồn siêu hiều quả",
                    price: 300000,
                    sale: 0,
                    quantityInStock: 7,
                },
            ]
        }
    },
    components: {
        ProductItem
    }
}
</script>

<style>

</style>
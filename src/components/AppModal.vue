<template>
  <div v-if="isOpen" class="modal" @click="handleClose">
    <div class="modal_container" @click.stop>
        <div class="modal_header">
            <h1 class="modal_title">Cart</h1>
            <div class="modal_close" @click="handleClose">
                <i class="fa fa-times"></i>
            </div>
        </div>
        <div class="modal_body">
            <slot></slot>
        </div>
        <div class="modal_footer">

        </div>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        isOpen: {
            type: Boolean
        },
        handleCloseModal: {
            type: Function,
        }
    },
    methods: {
        handleClose() {
            this.handleCloseModal();
        }
    }
}
</script>

<style>
.modal {
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    display: flex;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.4);
}
.modal_container {
    width: 950px;
    margin: auto;
    margin-top: 70px;
    background: white;
    border: 1px solid #880;
    padding: 10px 20px;
}
.modal_header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.modal_close {
    width: 50px;
    height: 50px;
    line-height: 50px;
    border-radius: 50%;
    text-align: center;
    font-size : 30px;
}
.modal_close:hover {
    background: rgba(0, 0, 0, 0.2);
    cursor: pointer;
}
</style>
<template>
<div v-if="showModal">
    <transition name="modal">
        <div class="modal-mask">
            <div class="modal-wrapper">
                <div class="modal-dialog" role="document">
                    <div class="modal-content">
                        <div class="modal-header">
                            <h5 class="modal-title">
                                Mi carrito
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart shoppingcart" viewBox="0 0 16 16">
                                    <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM3.102 4l1.313 7h8.17l1.313-7H3.102zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
                                </svg>
                            </h5>
                        </div>
                    <div class="modal-body">

                        <Cart :cart="cart" :deleteProduct="deleteProduct"/>
                    
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" @click="setShowModal">Cancelar</button>
                        <button type="button" class="btn btn-primary" @click="payment()" :disabled="cart.length>0 ?false :true">Pagar</button>
                    </div>
                </div>
            </div>
            </div>
        </div>
    </transition>
</div>

</template>

<script>
//content:
import Cart from '../components/Cart.vue';

export default {
    name: "Modal",
    props:{
        showModal:Boolean,
        setShowModal:Function,
        cart:Array,
        deleteProduct:Function,
        resetCart: Function
    },
    components:{
        Cart
    },
    methods:{
        payment(){
            alert("Pagado!!!!");
            this.resetCart();
        }
    }
}
</script>

<style scoped>
.modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
}

.modal-wrapper {
    display: table-cell;
    vertical-align: middle;
}
</style>


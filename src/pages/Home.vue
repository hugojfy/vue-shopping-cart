<template>
    <div>
        <NavBar :setShowModal="setShowModal" :setCategory="setCategory"/>
        <div class="seccion">
            <Container :productsData="productsList" :addProduct="addProduct" :cart="cart" />
        </div>
        <Modal :resetCart="resetCart" :showModal="showModal" :setShowModal="setShowModal" :cart="cart" :deleteProduct="deleteProduct" />
        <h1>Footer</h1>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue';
import Container from '../components/Container.vue';
import productsData from '../assets/json/productsData.json';
import Modal from '../components/Modal.vue';


export default {
    name: 'Home',
    components:{
        NavBar,
        Container,
        Modal,
    },
    data() {
        return {
            productsData,
            productsList:productsData,
            showModal:false,
            cart:[]

        }
    },
    methods:{
        setCategory(category){
            let auxArray=[];
            if(category==="all"){
                auxArray = this.productsData
            }else{
                auxArray = this.productsData.filter(item=>item.category===category);
            }
            this.productsList = auxArray;
        },
        setShowModal(){
            this.showModal=!this.showModal;
        },
        addProduct(product){
            this.cart.push(product);
        },
        deleteProduct(index){
            if (index > -1) {
                this.cart.splice(index, 1); // 2nd parameter means remove one item only
            }
        },
        resetCart(){
            this.cart=[];
        }
    },
}
</script>

<style scoped>
.seccion{
    min-height: calc( 100vh - 80px);
}
</style>
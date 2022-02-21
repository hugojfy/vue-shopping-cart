<template>

    <div class="row container-cards">       
        <div class="col col-lg-3 container-cards-item" v-for="product in productsData" :key="product.id">
            <div class="card">
                <div class="card-body">
                    <img lass="card-img-top " :src="product.img" :alt="product.title">
                    <h5 class="card-title">{{product.title}}</h5>
                    <p class="card-text">${{product.price}}.00</p>
                    <a @click="addProduct(product)" v-if="status(product.id)" class="btn btn-primary">Agregar al carrito</a>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: "Container",
    props:{
        productsData:Array,
        addProduct: Function,
        cart:Array,
        
    },
    methods:{
        status(index){
            let aux = true;

            this.cart.map(item=>{
                if(item.id===index){
                    aux = false;
                }
            })

            return aux;
        }
    }
    

}
</script>

<style scoped>
.container-cards{
    padding: 10px 90px 30px 90px;
}
.container-cards-item{
    margin: 10px 0px 10px 0px;
}

img{
    width: 100%;
    height: 180px;
    object-fit: cover;
}

</style>
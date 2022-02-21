<template>
    {{showModal}}
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <a class="navbar-brand" href="#"><img src="../assets/logo.png" class="nav-bar-brand-logo" alt="shopping chart"></a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
            <ul class="navbar-nav">
                <li class="nav-item active">
                    <a class="nav-link" @click="setCategory('all')">Todo </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" @click="setCategory('men')" >Hombre </a>
                </li>
                <li class="nav-item ">
                    <a class="nav-link" @click="setCategory('women')">Mujer </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" @click="setCategory('children')">Niño </a>
                </li>

            </ul>
        </div>
        <div class="form-inline">
            <a class=" nav-right-icon" @click="setShowModal">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart shoppingcart" viewBox="0 0 16 16">
                    <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM3.102 4l1.313 7h8.17l1.313-7H3.102zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
                </svg>
            </a>
        </div>
    </nav>
</template>

<script>
export default {
    name: "NavBar",
    component:{

    },
    props:{
        setCategory: Function,
        setShowModal:Function
    }
}
</script>
<style scoped>
    .nav-bar-brand-logo{
        width: 45px;
        margin: 0px 20px 0px 20px;
    }
    .nav-link{
        cursor: pointer;
    }
    .nav-right-icon{
        padding-left: 20px;
        padding-right: 20px;
        cursor: pointer;
    }

</style>
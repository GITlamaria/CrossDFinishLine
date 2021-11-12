<template>
    <div class="container-fluid row justify-content-center align-self-center h-100 main-header">   
        <!-- jumbotron with animation and transition on render -->
            <transition appear :duration="10000" name="bounce">
            <b-jumbotron :header="title" fluid class="jumbotron" >

                <!-- add image here??? -->
                
            </b-jumbotron>
            </transition>
        <slot/>
    </div>
</template>

<script>

// import ImageComponent from './ImageComponent.vue'
    export default {

components: {
    // ImageComponent,
},
        data() {
            return {
                title: 'Crossing the Finish Line!',

                // headerImg: {
                //     src: require('../assets/images/lace-up.jpg'),
                //     alt: "group of runners",
                //     title: " ",
                // }
            }
        }

    }
</script>

<style scoped>

 div {
     height: 5rem;
 }   
.container-fluid {
    padding-right:0;
    padding-left:0;
    margin-right:auto;
    margin-left:auto;
    padding-bottom:0;
    background: linear-gradient(45deg, #9eb5c4, #191970 80%);
    /* height: 8rem; */
    /* background-color: yellow; */
 }
    .jumbotron h1, p {
        font-weight: 500; 
        /* text-align: center;
        vertical-align: center; */
        color: #f3e230 !important;
        padding-bottom: 10rem!important;
        /* background-color: transparent!important; */
    }
    .jumbotron {
        background-color: transparent!important;
        
        /* padding-top: 1rem; */

    }

    /*animate the jumbotron */
    .bounce-enter-active {
        animation: bounceIn 5s;
    }
    /* .bounce-leave-active {
    animation: bounceIn 10s reverse;
    } */

    @keyframes bounceIn {
        0% {
            transform: scale(0.1);
            margin-left: 100%;
        }
        60% {
            transform: scale(1.25);  
        }
        100% {
            transform: scale(1);
            opacity: 3;
        }
    }
</style>



<template>
    <div class="container-fluid row justify-content-center align-self-center h-100 main-header">   
        <!-- jumbotron with animation and transition on render -->
            <transition appear :duration="10000" name="bounce">
                <b-jumbotron :header="title" fluid class="jumbotron" />
            </transition>
        <slot/>
    </div>
</template>

<script>

    export default {

        data() {
            return {
                title: 'Crossing the Finish Line!',
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
 }
    .jumbotron h1, p {
        font-weight: 500; 
        color: #f3e230 !important;
        padding-bottom: 10rem!important;
    }
    .jumbotron {
        background-color: transparent!important;
    }

    /*animate the jumbotron */
    .bounce-enter-active {
        animation: bounceIn 5s;
    }

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



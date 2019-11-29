<template>
    <div class="wrapper">
        <h1>TNC</h1>
        <div class="swapping-squares-spinner onright" :style="spinnerStyle">
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
        </div><h2 class="has-text-danger">SCANNING 21 INDIVIDUALS IN THE AREA</h2>
        <a  href="/details" class="button is-large centerme"><img class="photo" src="https://images-na.ssl-images-amazon.com/images/I/51cVxhj2DKL.png" width="100" /></a>

    </div>
</template>

<script>
    export default {
        name: 'connection_tnc',
        data: () => ({
            loading: false,
        }),

        methods: {
            doDelete: function() {

                window.location.href = '/path';
            },
            trying: function() {

                window.location.href = '/path';
            },
            wait: function(ms){
                var start = new Date().getTime();
                var end = start;
                while(end < start + ms) {
                    end = new Date().getTime();
                }
            },
            scan: function () {
                this.loading = true;
                this.wait(550);
                this.loading = false;

            }

        },
        components: { LongPress: require('vue-longpress') },
        watch: {

        },
    }


</script>


<style scoped>
    .wrapper {
        text-align: center;
        height:800px;
    }

    .centerme {
        margin-top:9%;
        height: 300px;
        width: 300px;
        opacity: 0.6;
        filter: alpha(opacity=60);
        background-color: black;
        color: white;
        font-size: 15px;
        font-weight: 600;
    }

    .photo{
        width:200px;
        height:200px;
    }

    h1{
        color: white;
        margin-right: 90%;
        font-size: 30px;
        font-weight: 900;
    }

    h2{
        color: white;
        margin-left: 80%;
        font-size: 12px;
        font-weight: 400;
    }

    .swapping-squares-spinner, .swapping-squares-spinner * {
        box-sizing: border-box;
        color: white;
    }

    .swapping-squares-spinner {
        height: 65px;
        width: 65px;
        position: relative;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        color: white;
    }

    .swapping-squares-spinner .square {
        height: calc(65px * 0.25 / 1.3);
        width:  calc(65px * 0.25 / 1.3);
        animation-duration: 1000ms;
        border: calc(65px * 0.04 / 1.3) solid #ff1d5e;
        margin-right: auto;
        margin-left: auto;
        position: absolute;
        animation-iteration-count: infinite;
    }

    .swapping-squares-spinner .square:nth-child(1) {
        animation-name: swapping-squares-animation-child-1;
        animation-delay: 500ms;
    }

    .swapping-squares-spinner .square:nth-child(2) {
        animation-name: swapping-squares-animation-child-2;
        animation-delay: 0ms;
    }

    .swapping-squares-spinner .square:nth-child(3) {
        animation-name: swapping-squares-animation-child-3;
        animation-delay: 500ms;
    }

    .swapping-squares-spinner .square:nth-child(4) {
        animation-name: swapping-squares-animation-child-4;
        animation-delay: 0ms;
    }

    @keyframes swapping-squares-animation-child-1 {
        50% {
            transform: translate(150%,150%) scale(2,2);
        }
    }

    @keyframes swapping-squares-animation-child-2 {
        50% {
            transform: translate(-150%,150%) scale(2,2);
        }
    }

    @keyframes swapping-squares-animation-child-3 {
        50% {
            transform: translate(-150%,-150%) scale(2,2);
        }
    }

    @keyframes swapping-squares-animation-child-4 {
        50% {
            transform: translate(150%,-150%) scale(2,2);
        }
    }

    .onright{
        margin-left:88%;
        color: white;
    }
</style>

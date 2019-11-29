<template>
    <div class="wrapper">
        <h1>TNC</h1>
        <div class="swapping-squares-spinner onright" :style="spinnerStyle">
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
        </div><h2 class="has-text-danger">SCANNING 24 INDIVIDUALS IN THE AREA</h2>
        <div class="box opacc centerme">

            <h3>Blood Pressure</h3>
            <div class="progress">
                <div class="bargreen" style="width:45%">
                    <p class="percent">110/70 mm</p>
                </div>
            </div>
            <br />
            <h3 style="margin-right: 70%;">Heart Rate</h3>
            <div class="progress">
                <div class="bargreen" style="width:55%">
                    <p class="percent">75 bpm</p>
                </div>
            </div>
            <br />
            <h3 style="margin-right: 70%;">Blood Sugar </h3>
            <div class="progress">
                <div class="baryellow" style="width:65%">
                    <p class="percent">145 mg/DL</p>
                </div>
            </div>
            <br />
            <h3 style="margin-right: 60%;">Body Temperature </h3>
            <div class="progress">
                <div class="barred" style="width:72%">
                    <p class="percent">107.5 F</p>
                </div>
            </div>
            <br />
            <h3 style="margin-right: 55%;">Overall Energy Levels</h3>
            <div class="progress">
                <div class="bargreen" style="width:94%">
                    <p class="percent">94%</p>
                </div>
            </div>
        </div>

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
    .opacc{
        opacity: 0.5;
        filter: alpha(opacity=60);
        background-color: black;
        height: 100px;
        width: 100px;

    }

    .wrapper {
        text-align: center;
        height:800px;
    }

    .centerme {
        margin-top:0.5%;
        margin-left:35%;
        height: 600px;
        width: 400px;
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
        margin-bottom: -2%;
    }

    h3{
        color: white;
        margin-right: 65%;
        font-size: 12px;
        font-weight: 600;
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
    .progress {
        margin:20px auto;
        padding:0;
        width:90%;
        height:30px;
        overflow:hidden;
        background:#e5e5e5;
        border-radius:6px;
    }

    .bargreen {
        position:relative;
        float:left;
        min-width:1%;
        height:100%;
        background:green;
        opacity: 50;
    }

    .barred {
        position:relative;
        float:left;
        min-width:1%;
        height:100%;
        background:red;
        opacity: 50;
    }

    .baryellow {
        position:relative;
        float:left;
        min-width:1%;
        height:100%;
        background:orange;
        opacity: 50;
    }

    .percent {
        position:absolute;
        top:50%;
        left:50%;
        transform:translate(-50%,-50%);
        margin:0;
        font-family:tahoma,arial,helvetica;
        font-size:12px;
        color:white;
    }
</style>

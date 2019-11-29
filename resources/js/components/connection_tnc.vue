<template>
    <div class="wrapper">
        <h1>TNC</h1>
        <longpress class="button is-large centerme" duration="5" pressing-text="Detecting {$rcounter}" action-text="Detected"><img class="photo" src="https://images-na.ssl-images-amazon.com/images/I/51cVxhj2DKL.png" width="100" /></longpress>
    </div>
</template>

<script>
    export default {
        name: 'connection_tnc',
        data: () => ({
        }),
        methods: {
            doDelete: function() {
                this.$refs.deleteButton.reset();
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
        margin-top:15%;
        height: 300px;
        width: 300px;
        opacity: 0.6;
        filter: alpha(opacity=60);
        background-color: black;
        color: white;
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
</style>

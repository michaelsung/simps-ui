<template>
    <div id="image-generator">
        <img v-if="loading" src="../assets/tail-spin.svg" />
        <img v-if="!loading" class="image animated fadeInDown" v-bind:src="img" />
        <p>
        <h1 v-if="!loading" class="animated fadeInUp">{{ caption }}</h1>

        <button v-if="!loading" class="animated fadeInUp" @click="getImage">{{ buttonLabel }}</button>
    </div>

</template>

<script>
import axios from 'axios';
export default {
    name: 'ImageGenerator',
    data() {
        return {
            caption: null,
            img: null,
            loading: false,
            buttonLabel: 'SIMP!'
        }
    },
    mounted() {
        this.caption = null;
        this.img = null;
    },
    methods: {
        getImage() {
            this.loading = true;
            this.caption = null;
            this.img = null;
            axios.get('http://localhost:3000/api/random')
            .then((response) => {
                console.log(response.data);
                this.caption = response.data.caption;
                this.img = response.data.url;
                this.loading = false;
            })
            this.buttonLabel = "SIMP AGAIN!"
        }
    }

  }
</script>

<style scoped>
.image {
    max-height:500px;
    max-width:500px;
    height:auto;
    width:auto;
    -webkit-animation-duration: 0.5s;
}

button {
    font-size: 40px;
    font-weight: bold;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    background-color: #ffbb22; /* Green */
   border: 2px solid #ffbb22;
   color: white;
   padding: 8px 16px;
   text-align: center;
   text-decoration: none;
   display: inline-block;
   font-size: 32px;
   margin: 4px 2px;
   -webkit-transition-duration: 0.1s; /* Safari */
   transition-duration: 0.1s;
   cursor: pointer;
}
button:hover {
    background-color: white;
    color: #2f64d6;
}
</style>

<template>
  <div>
    <div class="container-fluid" v-if="errored">
      <p>We're sorry, we're not able to retrieve this information at the moment, please try back.</p>
    </div>
    <!-- <div>
      <p v-for="item in list">
        Line:
        <span v-text="item"></span>
      </p>
      <infinite-loading @infinite="infiniteHandler"></infinite-loading>
    </div> -->
    <div class="container cards">
      <div class="row">
        <div v-for="product in products.data" class = "card col-lg-3 zoom">
          <img class="card-img-top" :src= "product.imgurl"  alt="Card image cap">
          <div class="card-body">
            <h4 class="card-title">{{ product.name }}</h4>
            <p class="card-text description">{{ product.descrption }}</p>
            <p class="card-text price">{{ product.price }} $</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import axios from 'axios';
import InfiniteLoading from 'vue-infinite-loading';

export default {
  data () {
    return{
      // list: [],
      products: [],
      loading: true,
      errored: false
    };
  },
  mounted () {
    axios
      .get('http://localhost:3000/api/v1/products')
      .then(response => (this.products = response.data))
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  },
  // methods: {
  //   infiniteHandler($state) {
  //     setTimeout(() => {
  //       const temp = [];
  //       for (let i = this.list.length + 1; i <= this.list.length + 20; i++) {
  //         temp.push(i);
  //       }
  //       this.list = this.list.concat(temp);
  //       $state.loaded();
  //     }, 1000);
  //   },
  // },
  // components: {
  //   InfiniteLoading
  // },
}
</script>


<style lang="scss">
.container-fluid {
  padding-top: 15px;
  background-color: transparent;
  text-align: center;
}

.zoom {
  transition: transform .2s;
  margin: 0 auto;
  background: white;
  text-align: center;
  border-top: transparent;
  border-left: transparent;
}

.zoom:hover {
  -ms-transform: scale(1.2);
  -webkit-transform: scale(1.2);
  transform: scale(1.2);
  z-index: 1;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.zoom:nth-of-type(4n+0) {
  border-right: transparent;
}

.description {
  color: #bfbfbf;
  font-weight: bolder;
}

.price {
  color: #ff9900;
  font-weight: bolder;
}

.cards {
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>

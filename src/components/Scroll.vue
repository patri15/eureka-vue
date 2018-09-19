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

</style>

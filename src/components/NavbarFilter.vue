<template>
  <div>
    <nav class='navbar nav-sort navbar-expand-md'>
      <div class='container'>
        <div class='row'>
          <button class='navbar-toggler nav-button-2' data-target='#collapsibleNavbar2' data-toggle='collapse' type='button'>
            <i class='fas fa-bars'></i>
          </button>
          <div class='collapse navbar-collapse' id='collapsibleNavbar2'>
            <ul class='navbar-nav'>
              <div class='col-lg-4 col-md-4 text-left'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop'>
                    CATEGORY
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                  <div class='dropdown-menu'>
                    <a class='dropdown-item' v-on:click="filterByCategory('Breakfast')">Breakfast</a>
                    <a class='dropdown-item' v-on:click="filterByCategory('Lunch')">Lunch</a>
                    <a class='dropdown-item' v-on:click="filterByCategory('Dinner')">Dinner</a>
                  </div>
                </li>
              </div>
              <div class='col-lg-3 col-md-3 text-left'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop'>
                    SORTING
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                  <div class='dropdown-menu'>
                    <a class='dropdown-item' v-on:click="filterByDescription('Entrees')">Entrees</a>
                    <a class='dropdown-item' v-on:click="filterByDescription('Second Courses')">Second Courses</a>
                    <a class='dropdown-item' v-on:click="filterByDescription('Salad')">Salads</a>
                    <a class='dropdown-item' v-on:click="filterByDescription('Pizza')">Pizza</a>
                    <a class='dropdown-item' v-on:click="filterByDescription('Deserts')">Deserts</a>
                  </div>
                </li>
              </div>
              <div class='col-lg-4 col-md-4 text-left'>
                <li class='nav-item dropdown'>
                  <a class='nav-link '  v-on:click="filterByVegetarian(true)" >
                    VEGETARIAN
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                </li>
              </div>
              <div class='col-lg-3 col-md-3'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop' style='color: black'>
                    PRICE
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                  <div class='dropdown-menu'>
                    <a class='dropdown-item' v-on:click="filterByPrice('true')">Ascending</a>
                    <a class='dropdown-item' v-on:click="filterByPrice('false')">Descending</a>
                  </div>
                </li>
              </div>
            </ul>
          </div>
        </div>
      </div>
    </nav>
    <div class="container cards">
      <div class="row">
        <div v-for="product in products.data" class = "card col-md-3 zoom">
          <img class="card-img-top" :src= "product.imgurl"  alt="Card image">
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

  export default {
    data () {
      return{
        products: []
      };
    },
    mounted () {
      axios
        .get('http://localhost:3000/api/v1/products')
        .then(response => (this.products = response.data))
    },
    methods: {
      filterByDescription(description) {
        axios.get('http://localhost:3000/api/v1/products',{params:{
          descrption: description
        }
        })
       .then(response => (this.products = response.data))
      },
      filterByCategory(productCategory) {
        axios.get('http://localhost:3000/api/v1/products',{params:{
          category: productCategory
        }
        })
        .then(response => (this.products = response.data))
      },
      filterByVegetarian(productVegetarian) {
        axios.get('http://localhost:3000/api/v1/products',{params:{
          vegetarian: productVegetarian
        }
        })
        .then(response => (this.products = response.data))
      },
      filterByPrice(productPrice) {
        axios.get('http://localhost:3000/api/v1/products',{params:{
          price: productPrice
        }
        })
        .then(response => (this.products = response.data))
      }
    }
  }
</script>

<style lang="scss">
  .nav-sort {
    background-color: #f2f2f2;

    .nav-link {
      color: black;
    }

    a {
      font-weight: bold;
    }

    span {
      font-weight: initial;
    }
  }

  .dropdown-menu {
    border-color: transparent;
  }

  .dropdown-toggle::after {
    display: none !important;
  }

  //product cards

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

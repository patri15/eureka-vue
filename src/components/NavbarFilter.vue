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
              <div class='col-lg-3 col-md-3 text-left'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop'>
                    CATEGORY
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                  <div class='dropdown-menu'>
                    <a class='dropdown-item' href='#'>Breakfast</a>
                    <a class='dropdown-item' href='#'>Lunch</a>
                    <a class='dropdown-item' href='#'>Dinner</a>
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
                    <a class='dropdown-item' href='#' v-for="product in filterBy(products, 'Entrees')">Entrees</a>
                    <a class='dropdown-item' href='#'>Second Courses</a>
                    <a class='dropdown-item' href='#'>Salads</a>
                    <a class='dropdown-item' href='#'>Deserts</a>
                  </div>
                </li>
              </div>
              <div class='col-lg-3 col-md-3 text-left'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop'>
                    VEGETARIAN
                    <i class='fas fa-angle-down' style='color: #ff9900'></i>
                  </a>
                  <div class='dropdown-menu'>
                    <a class='dropdown-item' href='#'>Entrees</a>
                    <a class='dropdown-item' href='#'>Second Courses</a>
                    <a class='dropdown-item' href='#'>Salads</a>
                    <a class='dropdown-item' href='#'>Deserts</a>
                  </div>
                </li>
              </div>
              <div class='col-lg-3 col-md-2'>
                <li class='nav-item dropdown'>
                  <a class='nav-link dropdown-toggle' data-toggle='dropdown' href='#' id='navbardrop' style='color: black'>
                    PRICE
                    <span class='rangeValues'></span>
                  </a>
                </li>
              </div>
              <div class='col-lg-3 col-md-2'>
                <li class='nav-item dropdown'>
                    <range-slider></range-slider>
                </li>
              </div>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import axios from 'axios';
import RangeSlider from 'RangeSlider.vue';

export default {
  components: {
    RangeSlider
  }
</script>

<style lang="scss">
.nav-sort {
  background-color: #f2f2f2;

  .nav-link {
    color: black;
  }

  // a {
  //   font-weight: bold;
  // }

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


// range slider

</style>

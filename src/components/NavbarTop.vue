<template>
  <nav class="navbar navbar-expand-md main-navbar navbar-dark">
  <div class="container">
    <a class="navbar-brand mb-0 h1" href="/">
      <div class="row">
        <img alt="logo" class="nav-logo" src="https://cdn.onlinewebfonts.com/svg/img_255075.png" style="height:50px;width:50px;"/>
        <span class="nav-title">
          EUREKA
          <br/>
          CAFFE
        </span>
      </div>
    </a>
    <button aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" class="navbar-toggler" data-target="#navbarSupportedContent" data-toggle="collapse" type="button">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto detail">
        <li class="nav-item">
          <!-- <%= link_to "Home", root_path, class: "nav-link active", id: 'hover-bg' %> -->
        </li>
        <li class="nav-item d-none d-lg-block d-xl-block">
          <i class="fas fa-circle"></i>
        </li>
        <li class="nav-item">
          <!-- <%= link_to "About", about_path, class: "nav-link  active", id: 'hover-bg' %> -->
        </li>
        <li class="nav-item d-none d-lg-block d-xl-block">
          <i class="fas fa-circle"></i>
        </li>
        <li class="nav-item">
          <!-- <%= link_to "Service", service_path, class: "nav-link  active", id: 'hover-bg' %> -->
        </li>
        <li class="nav-item d-none d-lg-block d-xl-block">
          <i class="fas fa-circle"></i>
        </li>
        <li class="nav-item">
          <!-- <%= link_to "Blog", blog_path, class: "nav-link  active", id: 'hover-bg' %> -->
        </li>
        <li class="nav-item d-none d-lg-block d-xl-block">
          <i class="fas fa-circle"></i>
        </li>
        <li class="nav-item">
          <!-- <%= link_to "Contacts", contacts_path, class: "nav-link  active", id: 'hover-bg' %> -->
        </li>
        <li class="nav-item d-none d-lg-block d-xl-block">
          <i class="fas fa-circle"></i>
        </li>
      </ul>
    </div>
  </div>
  </nav>

</template>

<script>
export default {
  data() {
    return{};
  }
}


</script>

<style lang="scss">
.container {
  background: transparent;
}

#hover-bg:hover {
  color:#ff9900;
  text-shadow: 0 0 3px black;
  -ms-transform: scale(1.1); /* IE 9 */
  -webkit-transform: scale(1.1); /* Safari 3-8 */
  transform: scale(1.1);
}

.navbar-brand {
  text-align: left;
  line-height: 1;
  text-shadow: none;
}

.nav-title {
  padding-top: none;
  padding-left: 10px;
  transition: transform .2s;
}

.nav-title:hover{
  color:#ff9900;
  text-shadow: 0 0 3px black;
  -ms-transform: scale(1.1); /* IE 9 */
  -webkit-transform: scale(1.1); /* Safari 3-8 */
  transform: scale(1.1);
}

.nav-item{
  text-shadow: none;
  transition: transform .2s;
}

.fa-circle {
  color:#ff9900;
  font-size: 5px;
}

.d-none {
  padding-top: 5px;
}

.scrolled {
  background-color: black;
}

.nav-menu {
  color: white;
  background-color: transparent;
  border-color: transparent;
}

</style>

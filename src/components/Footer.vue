<template>
  <footer >
    <div class='container-fluid opening'>
      <div class='row'>
        <div class='col-md-4'></div>
        <div class='col-md-4 text-center'>
          <h3>Opening Hours</h3>
          <h6>Everyday 10 AM - 11 PM</h6>
        </div>
        <div class='col-md-4'></div>
      </div>
    </div>
    <div class='container-fluid contact'>
      <div class='row'>
        <div class='col-md-4 text-left'>
          <p>Contact:</p>
          <p>eureka_caffe@example.com</p>
          <p>0123-456-789</p>
          <a class='small' href='url'>Privacy policy</a>
        </div>
        <div class='col-md-4 text-center'>
          <p>Check our profiles:</p>
          <i class='fab fa-facebook-f'></i>
          <i class='fab fa-instagram'></i>
          <i class='fab fa-twitter'></i>
        </div>
        <div class='col-md-4 text-right'>
          <p class='small'>Copyright @Eureka Caffe 2018</p>
        </div>
      </div>
    </div>
  </footer>

</template>

<script>
export default {

}
</script>

<style lang="scss">
.opening {
  background-color:black;
  color:#ff9900;
  text-shadow: none;
  margin-bottom: 0px;
  line-height: 1;

  .col-md-4 {
    padding: 15px;
  }
}

.contact {
  background-color: #ff9900 ;
  text-shadow: none;
  margin-bottom: 0px;
  padding-top: 25px;
  padding-bottom: 30px;
  line-height: 0.5;

  a {
    color:black;
  }

  a:hover {
    color:white;
  }

  .fab {
    padding-left: 20px;
    padding-right: 20px;
  }

  .fab:hover {
    color:white;
  }
}


</style>

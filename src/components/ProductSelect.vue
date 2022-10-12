<template>
  <div id="productSelect">
    <div class="productSelectHeader">
      <span>Purple Edition</span>
      <span>Black Edition</span>
      <span>White Edition</span>
      <span>Gold Edition</span>
    </div>
    <div id="productImages">
      <ProductSelectImage/>
      <ProductSelectImage/>
      <ProductSelectImage/>
      <ProductSelectImage/>
    </div>
  </div>
</template>

<script>
import ProductSelectImage from './ProductSelectImage.vue'

export default {
  name: 'ProductSelect',
  components: {
    ProductSelectImage
  },
  mounted() {
    this.checkAnimation();
    document.getElementById('scrollContainer').addEventListener('scroll', () => {
      this.checkAnimation();
    });
  },
  methods: {
    isElementInViewport(el){
      
      var rect = el.getBoundingClientRect();

      return (
          rect.top >= 0 &&
          rect.left >= 0 &&
          rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) && /* or $(window).height() */
          rect.right <= (window.innerWidth || document.documentElement.clientWidth) /* or $(window).width() */
      );
    },

    // Check if it's time to start the animation.
    checkAnimation() {
        console.log('checking anim')
        var elem = document.getElementById('productImages');

        // If the animation has already been started
        if(elem.classList.contains('fadeIn')) return;

        if (this.isElementInViewport(elem)) {
            // Start the animation
            elem.classList.add('fadeIn');
        }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  @media only screen and (max-width: 1000px) {
    #productSelect {
      overflow: scroll;
    } 

    .productSelectHeader {
      width: 1000px;
    }

    #productImages {
      width: 1000px;
    }
  } 

  #productImages {
    display: flex;
    justify-content: space-evenly;
  }

  #productImages > div {
    transition-duration: 1s;
    transform: translateX(-2000px);
  }

  .fadeIn > div {
    transform: translateX(0) !important;
  }

  #productImages div:nth-child(1) {
    transition-delay: .3s;
  }

  #productImages div:nth-child(2) {
    transition-delay: .2s;
  }

  #productImages div:nth-child(3) {
    transition-delay: .1s;
  }
  #productImages div:nth-child(4) {
    transition-delay: .0s;
  }

  .productSelectHeader span {
    font-size: 35px;
    line-height: 70px;
  }

  .productSelectHeader {
    display: flex;
    justify-content: space-evenly;
    text-align: center;
    border-radius: 20px;
    border: 1px solid #998675;
  }

  .productSelectHeader > span {
    width: 220px;
  }
</style>

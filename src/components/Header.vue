<template>
    <div class="Header">
        <div id="selection">
            <ProductSelectImage></ProductSelectImage>
            <ProductSelectImage></ProductSelectImage>
            <ProductSelectImage></ProductSelectImage>
            <ProductSelectImage></ProductSelectImage>
        </div>
        <div class="burgerMenuWrapper">
            <label for="checkbox" class="hamburger">
                <input type="checkbox" id="checkbox">
                <span class="line lineTop"></span>
                <span class="line lineMid"></span>
                <span class="line lineBot"></span>
            </label>
        </div>
        <img class="HeaderImg" src="./../assets/Logo.png">
        <div class="searchBarWrapper">
            <div class="SearchBar">
                <input>
                <MagnifyIcon class="icon"/>    
            </div> 
        </div>
    </div>
</template>

<script>
import MagnifyIcon from 'vue-material-design-icons/Magnify.vue'
import ProductSelectImage from './ProductSelectImage.vue';

export default {
    name: 'HeaderTemplate',
    components: {
    MagnifyIcon,
    ProductSelectImage
},
    mounted() {
        document.getElementById('checkbox').onclick = function(elem) {
            if(elem.target.checked)
                document.getElementById('selection').classList.add('selectionOpen');
            else
                document.getElementById('selection').classList.remove('selectionOpen');
        }
    },
}
</script>

<style scoped>
.Header {
  height: 70px;
  width: 100%;
  max-width: 1920px;
  position: fixed;
  background-color: transparent;
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;
}

.searchBarWrapper {
    width: 100%;
    display: flex;
    flex-direction: row-reverse;
    align-items: center;
}

.SearchBar{
  height: 25px;
  border: 1px solid #998675;
  background: #1f1f1f;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  margin-right: 30px;
  transition: 1s;
  width: 24px;
  border-radius: 22px;
  padding-left: 2px;
  padding-right: 2px;
}

.SearchBar:hover, .SearchBar:focus-within {
    width: 150px;
      border-radius: 10px;
  padding-left: 1%;
  padding-right: 1%;
    margin-right: 30px;
}

.SearchBar input {
    border: none;
    background-color: transparent;
    width: 100%;
}

.SearchBar input:focus {
    outline: none;
}

.HeaderImg {
  max-height: -webkit-fill-available;
}

.icon {
    height: 24px;
}

.burgerMenuWrapper {
    width: 100%;
}

#checkbox {
    display: none
}

.hamburger {
    position: relative;
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    cursor: pointer;
    width: 30px;
}

.line {
    position: absolute;
    background-color: white;
    border-radius: 10px;
    height: 5px;
    width: 30px;
    transition:
    transform .25s, opacity .35s;
}

.lineTop {
    transform: translateY(-7px)
}

.lineBot {
    transform: translateY(7px)
}

#checkbox:checked~.lineTop {
    transform: rotate(45deg)
}

#checkbox:checked~.lineMid {
    transform: translateX(16px);
    opacity: 0;
}
#checkbox:checked~.lineBot {
    transform: rotate(-45deg)
}

.selectionOpen {
    height: 300px !important;
    border: 1px solid #998675 !important;
}

.selectionOpen #image {
    height: 200px !important;
}

#selection {
    width: 100%;
    height: 0;
    transition: 1s;
    background-color: #1f1f1f;
    border-radius: 0 0 10px 10px;
    position: absolute;
    z-index: -1;
    border: 0px solid #998675;
    display: flex;
    align-items: flex-end;
    justify-content: space-evenly;
}

#selection #image {
    height: 0;
    width: 125px;
    transition: 1s;
    transition-delay: .7s;
    margin-bottom: 10px;
}

</style>
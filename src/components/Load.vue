<template>
     <!--LOAD SCREEN-->
    <div id="loadScreen">
      <p id="loader">Loading...</p>
    </div>
</template>
<script>
export default {
    name: 'load',
     /*LOADING*/
    created: function() {
      window.addEventListener("load", function() {
         const load = document.getElementById("loadScreen");
        load.style.display = "none"
      })
    }
}

</script>

<style scoped>
#loadScreen {
background: #000;
opacity: 1;
position: fixed;
z-index: 10;
width: 100vw;
height: 1600px;
top: 0px;
}
#loader {
  font-size: 2vh;
  color: #fff;
  text-align: center;
  width: 20vh;
  margin: 40vh auto;
}
</style>



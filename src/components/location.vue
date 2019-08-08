<template>
    <div id="location">
        <div class="wrapper">
            <section>
                <h2>Location</h2>
                <div class="wrap-location">

<!--MAPSS-->
<GmapMap
  :center="{lat:16.0650, lng:120.4012}"
  :zoom="8"
  map-type-id="terrain"
  :options="{
    fullscreenControl: false,
    mapTypeControl: false,
 }"
  class="imgg">
  
  <GmapMarker
    :key="index"
    v-for="(m, index) in markers"
    :position="m.position"
    :clickable="true"
    @click="center=m.position"/>
</GmapMap> 

<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui error aperiam tempore, quod repellendus voluptatum. Beatae enim veritatis expedita accusamus. Assumenda harum aliquam est explicabo animi quasi voluptatibus modi sint aliquid omnis tenetur illum id, in repellat tempore porro consequatur, labore autem ullam nisi, qui voluptatum. Nam, optio commodi aliquid laboriosam in eaque sequi possimus, reprehenderit asperiores aspernatur rem ducimus!</p>
                </div>
            </section>
        </div>
    </div>
</template>
<script>
export default {
    name: 'location',
    data() {
        return {
        markers: [
            {position: {lat: 16.0406, lng: 120.4314}}
          ],
        }
    }
}
</script>
<style scoped>
#location {
    height: 100vh;
    background-color: black;
    position: relative;
}
section {
    padding-top: 30px;
}
section h2 {
    color: #fff;
    font-size: 25px;
    text-align: center;
    margin-bottom: 40px;
}
.imgg {
    width: 100%;
    height: 250px;
    margin: 0 auto;
}
.wrap-location p {
    font-size: 12px;
    color: #fff;
    margin-top: 40px;
}
.wrap-location {
    width: 250px;
    margin: 0 auto;
}
@media only screen and (min-width: 600px) {
    .wrap-location {
    width: 550px;
    margin: 0 auto;
}
.imgg {
    height: 400px;
    margin: 0 auto;
}

}
@media only screen and (min-width: 1200px) {
        #location::before {
        content: '';
        width: 1.5vh;
        height: 55vh;
        display: block;
        position: absolute;
        background: #fff;
        top: 0vh;
        left: 30vh;
    }
        #location::after{
        content: '';
        width: 1.5vh;
        height: 55vh;
        display: block;
        position: absolute;
        background: #fff;
        bottom: 0vh;
        left: 20vh;
    }
    .wrap-location {
    width: 50vw;
    height: 50vh;
    margin: 0 auto;
}
.imgg {
    width: 100%;
    height: 100%;
}
section h2 {
    font-size: 4vh;
    margin-bottom: 10vh;
}
.wrap-location p {
    font-size: 1.5vh;
    color: #fff;
    margin-top: 3vh;
    width: 20vw;
}
}
</style>



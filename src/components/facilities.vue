<template>
    <div id="facilities">
        <div class="wrapper">
            <section>
                <h2>Facilities</h2>
               <div class="image-wrap" id="image-wrap">
                <img :src="require('../assets/facilities-picture.png')">
                <ul>
                    <li v-for="item in items" :key="item.Id">{{item}}</li>
                </ul>
                </div>
            </section>
        </div>
    </div>
</template>

<script>
export default {
    name: 'facilities',
    data() {
        return {
            items: ['Rooms', 'Swimming Pools', 'Restaurant', 'Wi-fi', 'Complementary Water', 'Medical Center', 'Garden and Pool Bars', 'Function', 'Gym']
        }
    },

}
</script>
<style scoped>
#facilities {
    height: 100vh;
    background: url('~@/assets/background-facilities-tab.png');
    background-size: cover;
    background-color: black;
    position: relative;
}
section {
    padding-top: 20px;
}
.image-wrap {
    width: 277px;
    margin: 0 auto;
}
section img {
    width: 100%;
    
}
section h2 {
color: #8C8585;
text-align: center;
font-size: 25px;
margin-bottom: 30px
}
section ul li {
    font-weight: bold;
    list-style-type: none;
    color: #8C8585;
    font-size: 15px;
}
section ul {
    padding: 30px 0px;
}
@media only screen and (min-width: 600px) {
    .image-wrap {
    width: 400px;
    margin: 0 auto;
}
}
@media only screen and (min-width: 960px) {
    section h2 {
        position: absolute;
        transform: rotate(-90deg);
        font-size: 100px;
        top: 200px;
        left: -50px
    }
    section {
        padding-top: 90px 
    }
}
@media only screen and (min-width: 1200px) {
    .image-wrap {
        display: flex;
        justify-content: space-between;
        width: 50vw;
        position: relative;
    }

    section h2 {
        font-size: 10vw;
        margin: 0;
        left: 0vh;
        top: 30vh;
        z-index: 1;
    }
    .image-wrap img {
        width: 30vw;
        margin-top: 20vh;
        margin-left: 10vh;
        z-index: 1;
    }
    .image-wrap ul li {
        font-size: 2vh;
    }
    .image-wrap ul {
        margin-right: 5vh;
        z-index: 1;
    }
    section::before {
        content: '';
        position: absolute;
        background: #fff;
        width: 60vh;
        height: 60vh;
        display: block;
        border-radius: 50%;
        left: 20vh;
    }
    #facilities::before {
        content: '';
        width: 1.5vh;
        height: 55vh;
        display: block;
        position: absolute;
        background: #fff;
        top: 0vh;
        right: 40vh;
    }
        #facilities::after {
        content: '';
        width: 50vh;
        height: 1.5vh;
        display: block;
        position: absolute;
        background: #fff;
        top: 40vh;
        right: 0vh;
    }
}
</style>



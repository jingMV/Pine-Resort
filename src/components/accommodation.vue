<template>
    <div id="accommodation">
        <div class="wrapper">
            <section>
                <h2>Accommodation</h2>
                <div class="content-wrapper">

                <div class="image-wrap">
                    <img class="pic-a" :src="require('../assets/accommodation-pictureA.png')">
                    <img class="pic-b" :src="require('../assets/accommodation-pictureB.png')">
                </div>
                <div class="cont">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio ipsa praesentium libero, ullam doloremque saepe aliquam ipsam magni ex error molestiae officiis? Maiores assumenda obcaecati sint odit labore ducimus suscipit facere quia tenetur hic rem eveniet a, perferendis recusandae error, nostrum aspernatur totam ad necessitatibus repudiandae. Natus quo incidunt nulla delectus odio beatae aut at saepe, ut eveniet laborum praesentium ipsam dolore inventore optio! Vero, et nulla cumque ratione minima adipisci eum blanditiis, corporis doloremque animi consequatur minus deserunt vitae?.</p>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio ad, blanditiis quibusdam accusantium saepe nulla quidem vel enim reiciendis autem cum vitae minus, velit incidunt, eligendi laboriosam. Explicabo, reiciendis magni.</p>
                </div>
                </div>
            </section>
        </div>
    </div>
</template>
<script>
export default {
    name: 'accommodation',
    
}
</script>

<style scoped>
#accommodation {
    height: 100vh;
    background: url(~@/assets/background-accommodation-tab.png);
    background-size: cover;
    background-repeat: no-repeat;
    position: relative;
}
section {
    padding-top: 40px
}
section h2 {
    color: #fff;
    text-align: center;
    font-size: 25px;
    margin-bottom: 30px;
}
.content-wrapper {
    width: 300px;
    margin: 0 auto
}
.content-wrapper p {
    color: #fff;
    font-size: 12px;
    margin-top: 40px;
}
.image-wrap {
    display: flex;
    justify-content: space-around;
}
.pic-a {
    width: 200px;
}
.pic-b {
    width: 100px;
}
@media only screen and (min-width: 600px) {
.content-wrapper {
    width: 550px;
    margin: 0 auto;
}
.pic-a {
    width: 350px;
}
.pic-b {
    width: 190px;
}
}
@media only screen and (min-width: 960px) {
    #accommodation {
        background:  url(~@/assets/background-accommodation-desktop.png);
        background-repeat: no-repeat;
        background-size: cover;
    }
}
@media only screen and (min-width: 1200px) {
    section {
        padding-top: 10vh;
    }
    section h2 {
        font-size: 4vh;
        margin-bottom: 5vh;
    }
    .content-wrapper {
        width: 55vw;
        display: flex;
        height: 30vh;
    }
    .content-wrapper p {
        font-size: 1.7vh;
        margin: 3vh 3vh 2vh 3vh;
    }
    .image-wrap {
        display: inherit;
    }
    .pic-a {
        width: 40vh;
    }
    .pic-b {
        position: absolute;
        width: 30vh;
        bottom: 5vh;
        left: 44.5vh;
    }
        
    section::before {
        content: '';
        background: url('~@/assets/logoss.png');
        width: 70vh;
        height: 70vh;
        background-size: 70vh;
        position: absolute;
        right: -30vh;
        bottom: -35vh;
        animation: logo-rotate 10s infinite;
        transition: 800ms;
        z-index: 1;
        
    }
    @keyframes logo-rotate {
        from {
            transform: rotate(0deg)
        }
        to {
            transform: rotate(360deg)
        }
    }
    #accommodation::before {
        content: '';
        width: 1.5vh;
        height: 55vh;
        display: block;
        position: absolute;
        background: #fff;
        top: 0vh;
        left: 30vh;
    }
        #accommodation::after{
        content: '';
        width: 1.5vh;
        height: 55vh;
        display: block;
        position: absolute;
        background: #fff;
        bottom: 0vh;
        left: 20vh;
    }
}
</style>



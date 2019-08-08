<template>
    <div id="section">
        <div class="wrapper">
            <section class="carousel-image">

               <!--
                <v-carousel hide-delimiters :show-arrows="false" cycle interval="10000" height="100vh" class="carousel-caontainer">
                <v-carousel-item 
                v-for="item in items" 
                :key="item.Id" :src="item.image">
                </v-carousel-item>
                </v-carousel>
                -->

             <v-toolbar absolute color="rgba(0, 0, 0, 0.5)" bottom height="130px" >
            <!--FORM-->
            <form @submit.prevent="validateBeforeSubmit" id="reservation">
                <div class="wrap-form">
            <div class="input-wrapper">
            <label for="check-in" class="labels">Check-in</label>
            <p>
                <input name="check-in"
                v-model="checkIn"
                v-validate="'required|date_format:dd/MM/yyyy'"
                placeholder="dd/mm/yyyy"
                type="text"
                :class="{'input': true, 'inputStyle': errors.has('check-in') }"><br>
                
                <span v-show="errors.has('check-in')" class="errorStyle">
                {{ errors.first('check-in') }}</span>
            </p>
            </div>

            <div class="input-wrapper">
            <label for="check-out" class="labels">Check-out</label>
            <p>
                <input name="check-out"
                v-model="checkOut"
                v-validate="'required|date_format:dd/MM/yyyy'"
                placeholder="dd/mm/yyyy"
                type="text"
                :class="{'input': true, 'inputStyle': errors.has('check-out') }"><br>
                
                <span v-show="errors.has('check-out')" class="errorStyle">
                {{ errors.first('check-out') }}</span>
            </p>
            </div>
            </div>
            <p>
                <v-btn type="submit">Submit</v-btn>
            </p>

            </form>
            </v-toolbar>
            </section>
            
        </div>
    </div>
</template>

<script>

export default {
    name: 'sectionCom',
    data() {
        return {
     items: [
        {image: require('../assets/section-3.png')},
        {image: require('../assets/section-1.png')},
        {image: require('../assets/section-2.png')},
        {image: require('../assets/section-4.png')},
        ],
    checkIn: '',
    checkOut: '',
    }
    },
    methods: {
    validateBeforeSubmit() {
      this.$validator.validateAll().then((result) => {
        if (result) {
          // eslint-disable-next-line
          alert('Form Submitted!');
        }
        alert('Correct them errors!');
      });
    }
  },

}

</script>

<style scoped>
#section {
    height: 100vh;
    width: 100vw;
}
.carousel-image {
    height: 100vh;
    position: relative;
    background: url('~@/assets/section-1.png');
    background-size: cover;
}
.labels {
    color: #d3ae18;
    font-size: 15px;
    font-weight: bold;
}
input {
    background: #fff;
    border-radius: 10px;
    padding: 5px;
    width: 120px;
}
.errorStyle {
    color: red;
    font-size: 10px;
    font-style: italic;
}
.inputStyle {
    border: 1px solid red;
}
form button {
    color: black;
    border: 1px solid black;
    padding: 5px 10px;
    font-weight: bold;
    margin: 0 auto;
    display: block

}
form {
    margin: 0 auto;
}
.wrap-form {
    display: flex;
}
.input-wrapper {
    margin-left: 10px;
}
@media only screen and (min-width: 700px) {
    input {
        width: 300px;
    }
}
</style>


<template>
    <div id="contact">
        <div class="wrapper">
            <section>
                <h2>Say Hello!</h2>
                <div class="wrap-form">
                    <form @submit.prevent="validateBeforeSubmit">
        <!--NAME-->
        <div class="input-wrapper">
            <label for="name" class="labels">Name</label>
            <p>
                <input name="name" 
                v-model="name" 
                v-validate="'required|alpha'" 
                :class="{'input': true, 'inputStyle': errors.has('name') }" 
                type="text"><br>

                <span v-show="errors.has('name')" 
                class="errorStyle">{{ errors.first('name') }}</span>
            </p>
        </div>

        <!--EMAIL-->
        <div class="input-wrapper" >
            
            <label for="email" class="labels">Email</label>
            <p>
            <input name="email"
            v-model="email"
            v-validate="'required|email'"
            :class="{'input': true, 'inputStyle': errors.has('email')}"
            type="email"><br>
            
            <span v-show="errors.has('email')" 
            class="errorStyle">{{ errors.first('email') }}</span>
            </p>
        </div>

        <!--PHONE NUMBER-->
        <div class="input-wrapper">
        <label for="phonenumber" class="labels">Phone Number</label>
            <p>
                <input name="phonenumber" 
                v-model="phonenumber" 
                v-validate="'required|numeric'" 
                :class="{'input': true, 'inputStyle': errors.has('phonenumber') }" 
                type="text"><br>

                <span v-show="errors.has('phonenumber')" class="errorStyle">
                {{ errors.first('phonenumber') }}</span>
            </p>
        </div>

        <!--MESSAGE-->
        <div class="input-wrapper">
            <v-text-field v-model="message"
            class="message-input" 
            label="message" name="message" 
            v-validate="'required'" dark>
            </v-text-field><br>
            <span v-show="errors.has('message')" 
            class="errorStyle">{{ errors.first('message') }}</span>
        </div>

        <!--BUTTON FORM-->
        <button type="submit">Send Message</button>
                    </form>
                </div>
            </section>
        </div>
    </div>
</template>
<script>
export default {
    name: 'contact',
    data() {
        return {
            name: '',
            email: '',
            phonenumber: '',
            message: '',
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
#contact {
    height: 100vh;
    background: url('~@/assets/background-contact-desktop.png');
    background-size: cover;
}
section {
    padding-top: 30px;
}
section h2 {
    font-size: 30px;
    font-weight: 400;
    text-align: center;
    color: #fff;
    margin-bottom: 50px;
}
.wrap-form {
    width: 230px;
    margin: 0 auto;
}
input {
    background: #fff;
    width: 100%;
    height: 40px;
    border-radius: 10px;
}
.labels {
    font-size: 13px;
    color: white;
}
.errorStyle {
    color: white;
    font-size: 12px;
    font-style: italic;
}
.inputStyle {
    border: 1px solid red;
}
.message-input {
    width: 100%;
}
form button {
    background: #fff;
    font-weight: bold;
    padding: 5px 8px;
}
@media only screen and (min-width: 960px) {
    #contact {
        background-position-y: -300px
    }
}
@media only screen and (min-width: 1200px) {
    #contact {
    background: url('~@/assets/about.png');
    background-size: cover;
    background-position-y: inherit;
    }
    section {
        padding-top: 10vh;
    }
    section h2 {
        font-size: 10vh;
    }
    .wrap-form {
    width: 30vw;
    height: 50vh;
    margin: 0 auto;
}
input {
    background: #fff;
    width: 100%;
    height: 7vh;
    border-radius: 10px;
}
.labels {
    font-size: 1.5vh;
    color: white;
}
.message-input {
    width: 100%;
    height: 6vh;
}
form button {
    background: #fff;
    font-weight: bold;
    padding: 1vh 1.5vh;
    font-size: 1.7vh;
    margin-top: 1vh;
}
}
</style>



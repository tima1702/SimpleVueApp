<template>
  <div class="rectangle-2"  id="login">
    <div>
      <div style="padding: 33px 30px 0 30px">
        <span class="log-in">Log In</span>
      </div>
      <div class="login-container" v-if="step === 1">
        <label class="label" for="email">Email</label>
        <input id="email" class="bg" v-model="email" placeholder="Enter email"/>
        <div style="text-align: center; width: 100%">
          <button class="color-blue" @click="sendEmaail">Continue</button>
        </div>
      </div>
      <div class="login-container" v-if="step === 2">
        <label class="label" for="pw">Password</label>
        <input id="pw" class="bg" v-model="pw" type="password" placeholder="Enter password"/>
        <div style="text-align: center; width: 100%">
          <button class="color-blue">Log In</button>
        </div>
      </div>
      <div class="rectangle-2-copy" v-if="step < 3">
        <span class="don-t-have-an-accoun">Don't have an account</span>
        <a class="sign-up">Sign Up</a>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        email: '',
        pw: '',
        step : 1,
        users: [{
          img: 'https://cdn3.iconfinder.com/data/icons/black-easy/512/538642-user_512x512.png',
          name: 'Nancy Pham',
          post: 'System Admin'
        },]
      }
    },
    methods:{
      checkEmail(){
        console.log(email)
        var re = /^([a-zA-Z0-9_\.\-])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
        return email ? !re.test(email.value) : true
      },
      sendEmaail(){
        this.step ++
      }
    }
  }
</script>

<style scoped>
  .rectangle-2 {
    margin: 120px auto 0;
    width: 420px;
    border-radius: 4px;
    background-color: #FFFFFF;
    box-shadow: 0 8px 24px 0 rgba(0,0,0,0.05), 0 1px 3px 0 rgba(0,0,0,0.05);
    font-family: 'Proxima Nova', sans-serif;
  }
  .log-in {
    color: #000000;
    font-size: 30px;
    font-weight: bold;
    line-height: 42px;
    text-align: center;
    display: block;
  }
  .label {
    color: #000000;
    font-size: 15px;
    line-height: 24px;
    display: block;
    text-align: left;
  }
  .bg {
    max-width: 336px;
    width: 100%;
    border: 1px solid #E4E9F1;
    border-radius: 2px;
    background-color: #FFFFFF;
    margin-bottom: 32px;
    display: block;
  }
   input.bg{
    padding: 6px 10px;
    color: #000000;
    font-size: 15px;
    line-height: 24px;
  }
  .color-blue {
    height: 46px;
    width: 148px;
    background-color: #4680FF;
    border: none;
    border-radius: 4px;
    color: #FFFFFF;
    font-size: 14px;
    font-weight: 600;
    line-height: 20px;
  }
  .rectangle-2-copy {
    border-radius: 0 0 4px 4px;
    background-color: #EFF3F6;
    padding: 18px 104px;
  }
  .don-t-have-an-accoun {
    color: #000000;
    font-size: 15px;
    line-height: 24px;
  }
  .sign-up {
   	color: #4680FF;
    font-size: 15px;
    line-height: 24px;
  }
  .login-container{
    padding: 30px 31px 28px 31px;
    display: block;
  }
  .user_img {
    width: 40px;
  }
  .jack-nguyen {
    color: #2A3547;
    font-size: 18px;
    font-weight: 600;
    line-height: 22px;
  }
  .company-admin {
    height: 18px;
    width: 172px;
    color: #2A3547;
    font-size: 15px;
    line-height: 18px;
  }
  .color-blue_log {
    height: 36px;
    width: 70px;
  }
</style>

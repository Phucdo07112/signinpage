<template>
    <div class="container">
        <div class="forms-container">
            <div class="signin-signup">
                <form action="" class="sign-in-form" v-if="!onSignin">
                    <h2 class="title">Welcome back</h2>
                    <p class="title-child">Welcome back! Please enter your details</p>
                    <div class="input-field">
                        <label for="">Email</label>
                        <input class="input-item" type="text" placeholder="Enter your email">
                    </div>
                    <div class="input-field">
                        <label for="">Password</label>
                        <input class="input-item" type="password" placeholder="Enter you password">
                    </div>
                    <div class="check-remember">
                        <div class="check-item">
                            <input type="checkbox" name="remember">
                            <label for="remember">Remember for 30 days</label>
                        </div>
                        <a href="" class="forgot">Forgot password</a>
                    </div>
                    <div class="btn-signin">
                        <button>Sign in</button>
                    </div>
                    <div class="btn-gg">
                        
                        <button><img src="../assets/images/search.png" alt="v">Sign in with Google</button>
                    </div>
                    <p class="title-question">Don't have account? <span @click="onToggleSignin" >Sign up</span></p>
                </form>
                <form action="" class="sign-in-form" v-if="onSignin">
                    <h2 class="title">Welcome back</h2>
                    <p class="title-child">Welcome back! Please enter your details</p>
                    <div class="input-field">
                        <label for="">Email</label>
                        <input class="input-item" type="text" placeholder="Enter your email">
                    </div>
                    <div class="input-field">
                        <label for="">Password</label>
                        <input class="input-item" type="password" placeholder="Enter you password">
                    </div>
                    <div class="input-field">
                        <label for="">Forgot Password</label>
                        <input class="input-item" type="fgpassword" placeholder="Enter you Forgot password">
                    </div>
                    <div class="check-remember">
                        <div class="check-item">
                            <input type="checkbox" name="remember">
                            <label for="remember">Remember for 30 days</label>
                        </div>
                        <a href="" class="forgot" style="color: #ff8906">Forgot password</a>
                    </div>
                    <div class="btn-signin">
                        <button style="background: #ff8906">Sign up</button>
                    </div>
                    <div class="btn-gg">
                        
                        <button><img src="../assets/images/search.png" alt="v">Sign in with Google</button>
                    </div>
                    <p class="title-question">Don't have account? <span @click="onToggleSignin" style="color: #ff8906">Sign in</span></p>
                </form>
            </div>
        </div>
        <div class="panels-container">
            <div class="globular" :style="{ 'background' : onSignin ? '#ff8906' : '#6440BE'}">
                <div class="blur"></div>
            </div>
        </div>
    </div>
</template>
<script>
  export default {
    data() {
        return {
            onSignin: false,
        }
    },
    methods: {
      onToggleSignin() {
        this.onSignin = !this.onSignin;
        
      }  
    },
  }
</script>
<style lang="css">
    .container {
        max-width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 100vh;
        transition: all .5s;
        
    }
    .forms-container {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
    }
    .forms-container .title {
        font-size: 50px;
        font-weight: 600;
        color: black;
    }
    .forms-container .title-child {
        font-size: 22px;
        color: #888B96;
        margin-bottom: 30px;
    }
    .sign-in-form {
        width: 100%;
    }
    
    .input-field {
        display: flex;
        justify-content: center;
        flex-direction: column;
        gap: 6px;
        margin-bottom: 15px;
    }
    .input-field label {
        color: #525862;
        font-size: 16px;
        font-weight: 600;
    }
    .input-item {
        width: 100%;
        height: 45px;
        border-radius: 6px;
        border: #D9DBDE solid 2px;
        padding: 10px;
    }
    .check-remember {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 20px 0 ;
    }
    .check-item {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 5px;
    }
    .check-item label {
        color: #525862;
        font-size: 16px;
        font-weight: 700;
    }
    .forgot {
        color: #7F56DA;
        font-weight: 700;
        font-size: 15px;
        
    }
    .btn-signin {
        margin-bottom: 20px;
    }
    .btn-signin button {
        width: 100%;
        height: 45px;
        border-radius: 6px;
        background-color: #7F56DA;
        color: #fff;
        font-weight: 500;
        border: none;
    }
    .btn-gg {
        margin-bottom: 40px;
    }
    .btn-gg button{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        width: 100%;
        height: 45px;
        border: #D9DBDE solid 2px;
        border-radius: 6px;
        background-color: #fff;
        color: #4D545C;
        font-weight: 700;
    }
    .btn-gg img {
        width: 25px;
    }
    .title-question {
        color: #888B96;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        width: 100%;
    }
    .title-question span {
        color: #7F56DA;
        font-weight: 700;
        font-size: 15px;
        cursor: pointer;
    }
    .panels-container {
        background-color: #F3F5F9;
        flex: 1;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .globular {
        position: relative;
        width: 250px;
        height: 250px;
        border-radius: 50%;
        transform: translateY(0px);
        animation: float 3s infinite linear;
    }
    .blur {
        position: absolute;
        width: 400px;
        height: 200px;
        background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0));
        backdrop-filter: blur(20px);
        -webkit-backdrop-filter: blur(20px);
        bottom: -75px;
        left: -75px;
    }

    @keyframes float {
        0%, 100%{
            transform: translateY(0rem);
        }
        50%{
            transform: translateY(-1rem);
        }
    }
    @media (max-width: 870px) {
        .container {
            flex-direction: column-reverse;
        }
        .signin-signup {
            width: 100%;
            margin: 0 15px;
        }
        .forms-container .title {
            font-size: 30px;
            text-align: center;
        }
        .panels-container {
            background-color: #fff;
            flex: 0;
            
        }
        .globular {
            width: 100px;
            height: 100px;
            margin-top: 40px;
        }
        .blur {
            width: 150px;
            height: 50px;
            left: -15px;
            bottom: -6px;
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }
        .forms-container .title-child {
            font-size: 15px;
            text-align: center;
        }
        @keyframes float {
            0%, 100%{
                transform: translateY(0rem);
            }
            50%{
                transform: translateY(0rem);
            }
        }
    }

</style>
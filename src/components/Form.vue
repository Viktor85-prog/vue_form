<template>
  <div class="hello">
    <div class="wrapper">
        <div class="wrapper__inner">
            <div class="wrapper__inner-content">
                <main class="page">
                    <section class="authorization authorization-main">
                        <div class="authorization-main__container">
                            <div class="authorization-main__wrapper">
                                <div class="authorization-main__body">
                                    <div class="authorization__title">Welcome back!</div>
                                    <div class="authorization__subtitle">Enter your credentials to access your account</div>
                                    <form action="#" name="#" class="authorization__form form-authorization">
                                        <label for="authorization-email">
                                            <div class="form-authorization__label">Email</div>
                                            <input type="text" class="form-authorization__input form-authorization__input_error" id="authorization-email" name="email" placeholder="name@company.com" autocomplete="off">
                                            <div class="form-authorization__error-text">Invalid email format</div>
                                        </label>
                                        <label for="authorization-password">
                                            <div class="form-authorization__label">Password</div>
                                            <input type="text" class="form-authorization__input" id="authorization-password" name="password" placeholder="Input your password" autocomplete="off">
                                            <!-- <div class="form-authorization__error-text">Password must be between 8 and 20 characters</div> -->
                                        </label>
                                        <a href="/forgot.html" class="form-authorization__link">Forgot password?</a>
                                        <button type="submit" class="form-authorization__button">Sign in</button>
                                    </form>
                                </div>
                            </div>
                        </div>
                    </section>
                </main>   
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import "./style.css"
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

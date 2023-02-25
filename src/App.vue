<template>
  <div id="app">
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
									<Form />
								</div>
                            </div>
                        </div>
                    </section>
                </main>   
            </div>
        </div>
    </div>
  </div>
  </div>
</template>

<script>
import Form from './components/Form.vue'
import "./style.css"


export default {
  name: 'App',
  components: {
    Form
  }
}
</script>

<style>

</style>

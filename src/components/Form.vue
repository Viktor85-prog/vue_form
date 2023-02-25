<template>
	<form @submit.prevent ="login" action="#" name="#" class="authorization__form form-authorization">
		<label for="authorization-email">
			<div class="form-authorization__label">Email*</div>
			<input 
				type="email" 
				v-model.trim ='$v.email.$model' 
				:class="{'form-authorization__input_error':validationStatus($v.email)}"
				class="form-authorization__input " 
				id="authorization-email" 
				name="email" 
				placeholder="name@company.com" 
				autocomplete="off">
			<div v-if ="!$v.email.required" class="form-authorization__error-text">Field is required</div>
			<div v-if ="!$v.email.email" class="form-authorization__error-text">Invalid email format</div>
		</label>
		<label for="authorization-password">
			<div class="form-authorization__label">Password*</div>
			<input 
				type="text" 
				v-model.trim ='$v.password.$model' 
				:class="{'form-authorization__input_error':validationStatus($v.email)}"
				class="form-authorization__input" 
				id="authorization-password" 
				name="password" 
				placeholder="Input your password" 
				autocomplete="off">
			<div v-if ="!$v.password.required" class="form-authorization__error-text">Field is required</div>
			<div v-if ="!$v.password.minLength" class="form-authorization__error-text">Password must have at least {{$v.password.$params.minLength.min}} letters.</div>
		</label>
		<a href="/forgot.html" class="form-authorization__link">Forgot password?</a>
		<button type="submit" class="form-authorization__button">Sign in</button>
	</form>
</template>

<script>
import { required, minLength, email } from 'vuelidate/lib/validators'

export default {
  name: 'Form',
  data() {
	return {
		email: '',
		password:''
	}
  },
  validations: {
    email: {
      required,
	  email
    },
    password: {
		required,
		minLength: minLength(8)
    }
  },
  methods: {
	resetData () {
		this.email = ''
		this.password =''
	},
	login() {
		this.$v.$touch()
		if(this.$v.pending || this.$v.$error) return

		var that = this
		
		that.$http.post(`https://api.corecruiter.org/api/user/auth`,{
			email: this.email,
			password:this.password
		})
		.then((response) => {
			console.log(response.data)
		})
		.catch(function (error) {
			console.log(error);
		});

		this.$v.$reset()
		this.resetData()
	},
	validationStatus (validation) {
		return typeof validation != "underfined" ? validation.$error :false
	}
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

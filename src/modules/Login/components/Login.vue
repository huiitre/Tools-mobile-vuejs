<template>
	<div class="login">
		<!-- <h1 class="login__title">Gestion Essence</h1> -->
		<form @submit.prevent="handleSubmit" class="login__form">
			<div class="login__form__username">
				<Input
					name="username"
					label="Identifiant"
					inputClass=""
					inputType="text"
					inputPlaceHolder="Identifiant"
					inputId="username"
					@onChangeValue="handleChangeInput"
				/>
			</div>
			<div class="login__form__password">
				<Input
					name="password"
					label="Mot de passe"
					inputClass=""
					inputType="password"
					inputPlaceHolder="Mot de passe"
					inputId="password"
					@onChangeValue="handleChangeInput"
				/>
			</div>
			<div class="login__form__submit">
				<button type="submit" class="login__form__submit-button">Se connecter</button>
			</div>
		</form>
	</div>
</template>

<script>
import Input from '@/modules/common/components/form/Input.vue'

export default {
	name: 'Login',
	components: {
		Input,
	},
	data() {
		return {
			credentials: {
				username: '',
				password: ''
			},
		}
	},
	methods: {
		handleChangeInput(data) {
			this.credentials[data.name] = data.value
		},
		handleSubmit() {
			this.$store.dispatch('User/login', this.credentials);
		}
	}
};
</script>

<style lang="scss">
//* composant login
.login {
	// height: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;

	//* titre H1
	/* &__title {
		margin: 3rem auto 0 auto;
		font-size: 2.5rem;
		text-align: center;
		border: 1px solid #fff;
		width: 90%;
		padding: 0.5rem;
		font-weight: bold;
	} */

	//* formulaire
	&__form {
		height: 50%;
		width: 60%;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;

		//* bloc email & bloc password
		&__username,
		&__password {
			font-size: 1.5rem;
			display: flex;
			flex-direction: column;
			text-align: center;
			height: 8rem;
			justify-content: space-evenly;
      margin-bottom: 2rem;

			//* input username & input password
			& input {
				height: 2rem;
				font-size: 1.5rem;
				text-align: center;
				font-weight: bold;
        border-radius: 10px;
			}
		}

		//* bloc submit (avec bouton)
		&__submit {
			width: 100%;
			height: 8rem;
			display: flex;
			flex-direction: column;
			justify-content: center;

			//* Bouton submit
			&-button {
				width: 100%;
        background-color: #476382;
				height: 2.5rem;
        font-size: 1rem;
        font-weight: bold;
        border: none;
        border-radius: 10px;
        color: #fff;
			}
		}
	}
}
</style>

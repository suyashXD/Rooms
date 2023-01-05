<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>
<style>
  .wrapper {
  text-align: center;
  display: inline-block;
  top: 50%;
  left: 50%;
}
  .login{
    border-radius: 20px;
    
  }
	.login:hover {
  background-color: #00BFA5; /* Green */
  color: black;
  border-radius: 20px;
	}
  /* .signup{
    border-radius: 20px;
    width: 40%;
  } */
	/* .signup:hover {
  background-color: #4CAF50; /* Green */
  /* color: white;
  border-radius: 20px;
	}
  .login,.signup{
    display: inline-block;
  } */
  label[for^=username] {
    color: black;
    font-weight: bold;
}
label[for^=password] {
    color: black;
    font-weight: bold;
}
</style>

<label for="username">Username</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password">Password</label>
<input name="password" bind:value={password} type="password" />

<div class="wrapper">
<button class="login" on:click={login}>Login</button>
<button class="login"  on:click={signup}>Sign Up</button>
</div>

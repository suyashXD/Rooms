<script>
  import { username, user } from './user';

  function signout() {
    user.leave();
    username.set('');
  }
  function refreshPage(){
    window.location.reload();
} 
</script>

<header>

<button class= "rooms" type="submit" onClick="window.location.href=window.location.href">Rooms</button>
  {#if $username}
    <div class="user-bio">
      
      <span>Hello <strong>{$username}</strong></span>
      <img src={`https://avatars.dicebear.com/api/initials/${$username}.svg`} alt="avatar" /> 
    </div>

    <button class="signout-button" on:click={signout}>Sign Out</button>

    {:else}

<button class = "hola" type="submit" onClick="window.location.href=window.location.href">💬</button>
  {/if}
</header>
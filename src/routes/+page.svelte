<script>
    
    let info = {}

    let userField;
    let passField;

    function login(){
        info['name'] = userField.value;
        info['pass'] = passField.value;
        console.log(info)
        
    }
</script>

<div class="n-reset" >
        <a href="/dashboard">asdfasdf</a>
        <nord-top-bar>
            <h1>Welcome to  Hack ' N ' Seek</h1>
          </nord-top-bar>
          
        <nord-stack style="max-width: 440px; margin: var(--n-space-xl) auto">
            <nord-banner shadow variant="warning">You’ve been signed out. Please sign in to continue.</nord-banner>
            <nord-card padding="l">
              <h1 slot="header">Sign in to NCB</h1>
              <form on:submit={login}>
                <nord-stack>
                  <nord-input
                    bind:this={userField}
                    label="Username"
                    id="user"
                    expand
                    required
                    hide-required
                    name="username"
                    type="email"
                    placeholder="user@example.com"
                  ></nord-input>
                  <nord-input
                    bind:this={passField}
                    label="Password"
                    id="pass"
                    expand
                    required
                    hide-required
                    name="password"
                    type="password"
                    placeholder="••••••••"
                  >
                  </nord-input>
                  <nord-button type="submit" expand variant="primary">Sign in</nord-button>
                </nord-stack>
              </form>
            </nord-card>

          </nord-stack>
          
</div>

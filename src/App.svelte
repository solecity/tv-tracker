<script>
  import "bootstrap/dist/css/bootstrap.min.css";
  import { Router, Route } from "svelte-navigator";
  import NavBar from "./NavBar/NavBar.svelte";
  import Films from "./Films/Films.svelte";
</script>

<Router>
  <header>
    <NavBar />
  </header>

  <main>
    <Route path="/*">
      <h1>Watching</h1>

      <h1>To Watch</h1>
    </Route>

    <Route path="films">
      <Films />
    </Route>

    <Route path="tvseries">
      <h3>About</h3>
      <p>That's what it's all about!</p>
    </Route>

    <Route path="animes">
      <h3>About</h3>
      <p>That's what it's all about!</p>
    </Route>

    <Route>
      <h3>Default</h3>
      <p>No Route could be matched.</p>
    </Route>
  </main>
</Router>

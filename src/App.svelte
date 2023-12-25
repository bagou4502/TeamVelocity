<script lang="ts">
  import { Router, Link, Route } from "svelte-routing";
  import Home from "./components/Home.svelte";
  import Home23 from "./components/Home23.svelte";
  import OAuthCallback from './components/OAuthCallback.svelte';

  export let url = "";
</script>

<Router {url}>
  <nav>
    <Link to="/">Home</Link>
    <Link to="/2">Home 23</Link>
  </nav>
  <div>
    <Route path="/"><Home /></Route>
    <Route path="/2"><Home23 /></Route>
  </div>
</Router>
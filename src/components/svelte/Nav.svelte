<script>
    import { slide } from "svelte/transition";
    import {quadInOut} from 'svelte/easing'
  import ResponsiveNav from "./ResponsiveNav.svelte";
  import {navToggle} from '../../store/store'
  let windowW
  
</script>

<svelte:window bind:innerWidth={windowW} />

<nav>
  <div class="logo"></div>
  {#if $navToggle && windowW < 700}
  <div class="nav"  transition:slide={{axis: 'x', duration: 500, easing: quadInOut}}>
    <ResponsiveNav />

  </div>
  {/if}
  
  
  {#if windowW > 700 }
    <ul >
      <li><a href="#accueil">ACCUEIL</a></li>
      <li><a  href="#services">SERVICES</a></li>
      <li><a  href="#produits">PRODUITS</a></li>
      <li><a  href="#contacts">CONTACTS</a></li>
    </ul>
  {/if}

  {#if windowW < 700}
    
  <button class="navBtn" on:click={() => {$navToggle = !$navToggle}}  >
    <span></span>
    <span></span>
  </button>
  {/if}
  
</nav>



<style >
  nav {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 5vw;

  }

  .nav {
    height: 100dvh;
    width: 100dvw;
    position: fixed;
    top: 0;
    right: 0;
  }
    ul {
      display: flex;
      align-items: ce;
      justify-content: center;
      gap: 20px;
    }

    li {
      overflow: hidden;
      padding: 3px 0;
    }

  .logo {
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: var(--primary-button);
  }

  a {
    color: var(--text);
    position: relative;
  }

  a:hover {
    color: var(--primary-button);
  }

  a::before, a::after {
    content: "";
    position: absolute;
    display: block;
    width: 100%;
    height: 2px;
    background-color: var(--accent);
    bottom: -1px;
  }

  a::before {
    transform-origin: -100% 0;
    transform: scaleX(1);
    transition: transform 0.3s ease-out;
  }
  a::after {
    transform-origin: 100% 0;
    transform: scaleX(1);
    transition: transform 0.3s ease-out;
  }

  a:hover::after {
    transform-origin: 0 0;
    transform: scaleX(0);
  }
  a:hover::before {
    transform-origin: 100% 0;
    transform: scaleX(0);
  }

  button {
    position: relative;
    background: none;
    border: none;
    outline: none;
    height: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 5px;
  }

  button span {
    background-color: var(--accent);
    display: block;
    height: 3px;
    width: 30px;
    
    
  }

  

  @media (max-width: 550px) {
    ul {
      display: none;
    }
  }
</style>
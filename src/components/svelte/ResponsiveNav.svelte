<script>
  import {navToggle} from '../../store/store'
</script>

<div>
  <ul class="links">
    <li><a  on:click={() => {$navToggle = false}} href="/">ACCUEIL</a></li>
    <li><a  on:click={() => {$navToggle = false}} href="#services">SERVICES</a></li>
    <li><a  on:click={() => {$navToggle = false}} href="#produits">PRODUITS</a></li>
    <li><a  on:click={() => {$navToggle = false}} href="#contacts">CONTACTS</a></li>
  </ul>

  <ul class="socail">
    <li>
      <a href="https://www.facebook.com/profile.php?id=100064108421949" target="_blank">
        <span>
          <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24"><path fill="currentColor" d="M13.355 22v-9.123h3.062l.459-3.555h-3.52v-2.27c0-1.03.285-1.731 1.761-1.731L17 5.32V2.14A25.233 25.233 0 0 0 14.257 2c-2.715 0-4.573 1.657-4.573 4.7v2.622h-3.07v3.555h3.07V22h3.671Z"/></svg>
        </span>
      </a>
    </li>
    <li>
      <a href="mailto:yvenoz.services@outlook.fr"><span><svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24"><path fill="currentColor" d="M19 22q-1.65 0-2.825-1.175T15 18v-4.5q0-1.05.725-1.775T17.5 11q1.05 0 1.775.725T20 13.5V18h-2v-4.5q0-.2-.15-.35T17.5 13q-.2 0-.35.15t-.15.35V18q0 .825.588 1.413T19 20q.825 0 1.413-.588T21 18v-4h2v4q0 1.65-1.175 2.825T19 22ZM3 18q-.825 0-1.413-.588T1 16V4q0-.825.588-1.413T3 2h16q.825 0 1.413.588T21 4v6h-3.5q-1.45 0-2.475 1.025T14 13.5V18H3Zm8-7l8-5V4l-8 5l-8-5v2l8 5Z"/></svg></span></a>
    </li>
  </ul>
</div>

<style>
  div {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-around;
    background-color: var(--primary);
    
  }

  .links {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    /* color: var(--primary-button); */
  }

  li a {
    color: var(--primary-button);
    font-size: 1.5rem;
  }

  .socail {
    display: flex;
    align-items: center;
    gap: 10px;
  }
</style>
<template>
  <header>
    <nuxt-link to="/" class="logo">
      <img class="shcp" src="~/assets/SHCP.svg" alt="logo">
    </nuxt-link>
    <input type="checkbox" id="nav-toggle" class="nav-toggle">
    <nav>
      <ul>
        <li>
          <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/work">Work</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/contact">Contact</nuxt-link>
        </li>
      </ul>
    </nav>
    <label for="nav-toggle" class="nav-toggle-label">
      <span></span>
    </label>
  </header>
</template>

<script>
export default {}
</script>
<style>
/* navigation styles start here */
header {
  background: #000;
  text-align: center;
  position: fixed;
  z-index: 999;
  width: 100%;
}
.logo {
  height: 80px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.shcp {
  width: 160px;
}
.nav-toggle {
  display: none;
}
.nav-toggle-label {
  position: absolute;
  top: 0;
  left: 0;
  margin-left: 1em;
  height: 100%;
  display: flex;
  align-items: center;
}
.nav-toggle-label span,
.nav-toggle-label span::before,
.nav-toggle-label span::after {
  display: block;
  background: white;
  height: 2px;
  width: 2em;
  border-radius: 2px;
  position: relative;
  transform: rotate(0deg);
	opacity: 1;
}
.nav-toggle-label span::before,
.nav-toggle-label span::after {
  content: '';
  position: absolute;
  transition: transform 0.35s ease-in-out;
}
.nav-toggle-label span {
  transition: opacity 1s ease-in-out;
}
.nav-toggle-label span::before {
  bottom: 7px;
}
.nav-toggle-label span::after {
  top: 7px;
}
.nav-toggle:checked ~ label span {
  height: 12px;
	opacity: 1;
	background-color: transparent;
}
.nav-toggle:checked ~ label span::before{
  position: relative;
	left: 0;
	top: 7px;
	transform: rotate(135deg);
	opacity: 0.9;
}
.nav-toggle:checked ~ label span::after{
  position: relative;
	left: 0;
	top: 5px;
	transform: rotate(-135deg);
	opacity: 0.9;
}
nav {
  position: absolute;
  text-align: left;
  top: 100%;
  left: 0;
  background: #000;
  width: 100%;
  transform: scale(1, 0);
  transform-origin: top;
  transition: transform 400ms ease-in-out;
}
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  margin-bottom: 1em;
  margin-left: 1em;
}
nav a {
  color: white;
  text-decoration: none;
  font-size: 1rem;
  text-transform: uppercase;
  opacity: 0;
  transition: opacity 150ms ease-in-out;
}
.nav-toggle:checked ~ nav {
  transform: scale(1, 1);
}
.nav-toggle:checked ~ nav a {
  opacity: 1;
  transition: opacity 250ms ease-in-out 250ms;
}

@media screen and (min-width: 1024px) {
  .nav-toggle-label {
    display: none;
  }
  header {
    display: grid;
    grid-template-columns: 1fr auto minmax(600px, 3fr) 1fr;
  }
  .logo {
    grid-column: 2 / 3;
    height: 80px;
    display: flex;
    align-items: center;
  }
  nav {
    all: unset;
    grid-column: 3 / 4;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }
  nav ul {
    display: flex;
  }
  nav li {
    margin-left: 3em;
    margin-bottom: 0;
  }
  nav a {
    opacity: 1;
    position: relative;
  }
  nav a::before {
    content: '';
    display: block;
    height: 2px;
    background: white;
    position: absolute;
    bottom: -0.7em;
    left: 0;
    right: 0;
    transform: scale(0, 1);
    transform-origin: left;
    transition: transform linear 250ms;
  }
  nav a:hover::before {
    transform: scale(1, 1);
  }
}
</style>

<script setup>
document.addEventListener('DOMContentLoaded', () => {

  // Get all "navbar-burger" elements
  const $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0);

  // Add a click event on each of them
  $navbarBurgers.forEach( el => {
    el.addEventListener('click', () => {

      // Get the target from the "data-target" attribute
      const target = el.dataset.target;
      const $target = document.getElementById(target);

      // Toggle the "is-active" class on both the "navbar-burger" and the "navbar-menu"
      el.classList.toggle('is-active');
      $target.classList.toggle('is-active');

    });
  });

});
</script>

<template>
  <nav class="navbar is-dark" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <router-link to="/" class="navbar-item">
        <img src="@/assets/logo.png" width="90" height="57">
      </router-link>

      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Device Management
          </a>

          <div class="navbar-dropdown">
            <router-link to="/" class="navbar-item">Device Search</router-link>
            <router-link to="/" class="navbar-item">Add Device</router-link>
            <router-link to="/" class="navbar-item">Device Status Override</router-link>
          </div>
        </div>
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            User Management
          </a>

          <div class="navbar-dropdown">
            <router-link to="/" class="navbar-item">Users</router-link>
            <router-link to="/" class="navbar-item">Add User</router-link>
          </div>
        </div>
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Client Management
          </a>

          <div class="navbar-dropdown">
            <router-link to="/" class="navbar-item">Clients</router-link>
            <router-link to="/" class="navbar-item">Add Client</router-link>
          </div>
        </div>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light">
              Log in
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>

</style>
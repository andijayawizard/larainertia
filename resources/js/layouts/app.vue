<template>
  <div>
    <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
      <div class="container">
        <inertia-link class="navbar-brand" href="/">LARAVEL + INERTIA.JS</inertia-link>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarCollapse"
          aria-controls="navbarCollapse"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul v-if="auth.user" class="navbar-nav me-auto mb-2 mb-md-0">
            <li class="nav-item">
              <inertia-link class="nav-link" href="/admin/dashboard"
                >DASHBOARD</inertia-link
              >
            </li>
            <li class="nav-item">
              <inertia-link class="nav-link" href="/posts/">POSTS</inertia-link>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="https://santrikoding.com/ebook" target="_blank"
                >EBOOK</a
              >
            </li>
            <li class="nav-item">
              <a
                class="nav-link"
                href="https://santrikoding.com/tutorial-set"
                target="_blank"
                >TUTORIAL SET</a
              >
            </li>
            <li class="nav-item">
              <inertia-link class="nav-link" href="/logout" method="POST"
                >LOGOUT</inertia-link
              >
            </li>
          </ul>
          <ul v-else class="navbar-nav ms-auto mb-2 mb-md-0">
            <li class="nav-item">
              <inertia-link class="nav-link" href="/login">LOGIN</inertia-link>
            </li>
            <li class="nav-item">
              <inertia-link class="nav-link" href="/register">REGISTER</inertia-link>
            </li>
          </ul>
          <form class="d-flex">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-success" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>

    <main class="container mt-5">
      <slot />
    </main>
  </div>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";
import { InertiaProgress } from "@inertiajs/progress";

InertiaProgress.init({
  // The delay after which the progress bar will
  // appear during navigation, in milliseconds.
  delay: 250,

  // The color of the progress bar.
  color: "#29d",

  // Whether to include the default NProgress styles.
  includeCSS: true,

  // Whether the NProgress spinner will be shown.
  showSpinner: false,
});
export default {
  //register Link di component
  components: {
    Link,
  },

  props: {
    auth: Object,
  },
};
</script>

<style scoped>
.mt-5 {
  margin-top: 100px !important;
}
</style>

<script>
import Main from './components/main.vue'
import emailjs from "@emailjs/browser"
export default {
  name:"App",
  components: {
    Main
  },
  data() {
    return {
      isLoading:true,
    };
  },

  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    },5000);
    let active = localStorage.getItem("user-theme");
    const changeTheme = this.getTheme() || this.getPreference();
    this.setTheme(changeTheme);
  },
  methods : {
    getTheme() {
      return localStorage.getItem("user-theme");
    },
    setTheme(theme) {
        localStorage.setItem("user-theme", theme);
        this.userTheme = theme;
        document.documentElement.id = theme;
      },
    getPreference() {
        const DarkPre = window.matchMedia(
          "(prefers-color-scheme : dark)"
        ).matches;
        if (DarkPre) {
          return "dark-theme";
        } else {
          return "light-theme";
        }
      },
  }
};
</script>

<template>
  <div v-if="isLoading" id="load">
    <h3 class='space'>Dev<span>Ebuka</span></h3>
  </div>
  <Main v-else />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>

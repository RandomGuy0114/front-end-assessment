<template class="header__template">
  <nav class="header__container">
    <!-- header 1 -->
    <div class="header__row1 .container">
      Covid 19 Response: No one should be left behind.Check out our different
      ways of helping schools and institutions during the pandemic
      <p class="header__row1-arrow">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M17.25 8.25L21 12m0 0l-3.75 3.75M21 12H3"
          />
        </svg>
      </p>
    </div>
    <!-- header 2 -->
    <ul  :class="['header__row2', { 'is-active': navOpen }]">
      <li>
        <span>
          <a :href="links[0].id">
            <img src="/src/assets/logo.png" alt="" />
          </a>
        </span>
      </li>
      <li v-for="link in links" :id="link.id">
        <a
          :href="link.link"
          @click="toggleNav"
          :class="[
            { 'header__row2-btn': link.title === 'BOOK A DEMO' },
            'header__row2-link',
            
          ]"
        >
          {{ link.title }}</a
        >
      </li>
    </ul>
    <div :class="['header-sm__screen', { 'is-active': navOpen }]">
      <span class="sm__screen-logo">
        <a :href="links[0].id">
          <img src="/src/assets/logo.png" alt="" />
        </a>
      </span>
      <button
        aria-labal="mobile nav button"
        @click="toggleNav"
        :class="['header__bars', { 'is-active': navOpen }]"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M3 6.75A.75.75 0 013.75 6h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 6.75zM3 12a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 12zm0 5.25a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75a.75.75 0 01-.75-.75z"
            clip-rule="evenodd"
          />
        </svg>
      </button>
    </div>
  </nav>
</template>

<script lang="ts">
export default {
  data() {
    return {
      navOpen: false,
      activePage:false,
      links: [
        { id: "home", title: "Home", link: "#home" },
        { id: "about-us", title: "About us", link: "#about-us" },
        { id: "products", title: "Products", link: "" },
        { id: "blogs", title: "Blogs", link: "#blogs" },
        { id: "contact", title: "Contact", link: "#contact" },
        { id: "book-a-demo", title: "BOOK A DEMO", link: "#book-a-demo" },
      ],
    };
  },
  methods: {
    toggleNav() {
      this.navOpen = !this.navOpen;
    },
  },
};
</script>

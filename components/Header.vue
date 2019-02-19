<template>
  <header>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/">Index</nuxt-link>
          <nuxt-link to="/movies">Movies</nuxt-link>
          <nuxt-link to="/about">About</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
header {
  width: 100%;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #521751;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

li {
  margin: 0 10px;
}

a {
  text-decoration: none;
  color: white;
}
</style>

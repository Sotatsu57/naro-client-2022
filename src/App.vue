<template>
  <main>
    <div :class="$style.container">
      <header :class="$style.header">
        <router-link to="/">Home</router-link>
        |
        <router-link to="/axios">Axios</router-link>
        |
        <!--         <router-link to="/countries/jpn">JPN</router-link>
        | -->
        <router-link to="/countries">CountryList</router-link>
        |
        <!--         <router-link to="/city/Hiroshima">Hiroshima</router-link>
        | -->
        <router-link to="/login">Login</router-link>
      </header>

      <router-view />
    </div>
  </main>
</template>

<style module>
.container {
  max-width: fit-content;
  margin: auto;
}
.header {
  display: flex;
  justify-content: center;
}
</style>

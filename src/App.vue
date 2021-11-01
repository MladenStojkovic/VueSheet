<template>
  <div id="app">
    <div id="nav">
      <nav class="navbar navbar-dark sticky-top bg-badin flex-md-nowrap p-0">
        <router-link class="col-sm-3 col-md-1 mr-0 logo-bar" to="/"> <div class="logo-wrapper"><img src="./assets/logo.png" alt="y"></div> </router-link>
        <ul class="navbar-nav px-3">
          <li class="nav-item text-nowrap">
            <router-link class="nav-link" to="/add">+ Add New Row</router-link>
          </li>
        </ul>
      </nav>
    </div>
    <router-view/>
  </div>
</template>

<style>
.container {
  max-width: 960px;
}

.border-top { border-top: 1px solid #e5e5e5; }
.border-bottom { border-bottom: 1px solid #e5e5e5; }
.border-top-gray { border-top-color: #adb5bd; }

.box-shadow { box-shadow: 0 .25rem .75rem rgba(0, 0, 0, .05); }

.lh-condensed { line-height: 1.25; }

.bg-badin {
  background-color: #0A7FB7;
}

.logo-wrapper {
  height: 50px;
}

.logo-wrapper img {
  height: 100%;
}

.logo-bar {
  background: white;
}
</style>

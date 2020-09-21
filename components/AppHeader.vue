<template>
  <b-navbar>
    <template slot="brand">
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="https://ethereum.org/static/21c418bf00f87ff4d4b83e3499ddb391/1d713/ethereum-logo-wireframe.png"
          alt="Lightweight UI components for Vue.js based on Bulma"
        />
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item>
        <nuxt-link to="/">Home</nuxt-link>
      </b-navbar-item>
      <b-navbar-item>
        <nuxt-link to="/about">About</nuxt-link>
      </b-navbar-item>
      <b-navbar-dropdown label="API CALLS">
        <b-navbar-item>
          <nuxt-link to="/gas-prices">Gas Prices</nuxt-link>
        </b-navbar-item>
        <b-navbar-item>
          <nuxt-link to="/prediction-table">Prediction Table</nuxt-link>
        </b-navbar-item>
      </b-navbar-dropdown>
    </template>
  </b-navbar>
</template>
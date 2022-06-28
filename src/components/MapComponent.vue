<template>
  <v-container>
    <v-card>
      <div id="sidebar" class="sidebar collapsed">
        <div class="sidebar-tabs">
          <ul role="tablist">
            <li>
              <a href="#home" role="tab">
                <i class="fa fa-bars"></i>
              </a>
            </li>
            <li class="disabled">
              <a href="#messages" role="tab">
                <i class="fa fa-envelope"></i>
              </a>
            </li>
            <li>
              <a href="https://github.com/Turbo87/sidebar-v2" target="_blank" role="tab">
                <i class="fa fa-github"></i>
              </a>
            </li>
          </ul>
          <ul role="tablist">
            <li>
              <a href="#settings" role="tab">
                <i class="fa fa-gear"></i>
              </a>
            </li>
          </ul>
        </div>
        <div class="sidebar-content">
          <div class="sidebar-pane" id="home">
            <h1 class="sidebar-header">
              Sidebar-V2
              <span class="sidebar-close">
                <i class="fa fa-caret-left"></i>
              </span>
            </h1>
            <p>
              A responsive sidebar for mapping libraries like
              <a href="http://leafletjs.com/">Leaflet</a>.
            </p>
            <p class="lorem">
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
              eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
              voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
              nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
              diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet.
            </p>

            <p class="lorem">
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
              eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
              voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
              nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
              diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet.
            </p>

            <p class="lorem">
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
              eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
              voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
              nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
              diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet.
            </p>

            <p class="lorem">
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
              eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
              voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
              nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
              diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
              clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
              amet.
            </p>
          </div>
          <div class="sidebar-pane" id="profile">
            <h1 class="sidebar-header">
              <span class="sidebar-close">
                <i class="fa fa-caret-left"></i>
              </span>
            </h1>
          </div>
          <div class="sidebar-pane" id="messages">
            <h1 class="sidebar-header">
              Messages
              <span class="sidebar-close">
                <i class="fa fa-caret-left"></i>
              </span>
            </h1>
          </div>
          <div class="sidebar-pane" id="settings">
            <h1 class="sidebar-header">
              Settings<span class="sidebar-close"><i class="fa fa-caret-left"></i></span>
            </h1>
          </div>
        </div>
      </div>
      <div id="map"></div>
    </v-card>
  </v-container>
</template>

<script>
// import { } from 'sidebar-v2';
// import "sidebar-v2/css";
import L from "leaflet";
import "leaflet/dist/leaflet.css";
export default {
  name: "MapComponent",
  data: () => ({
    map: null,
    sidebar: null,
  }),
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      this.map = L.map("map");
      this.map.setView([51.2, 7], 9);
      L.tileLayer("http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
        maxZoom: 18,
        attribution: "Map data &copy; OpenStreetMap contributors",
      }).addTo(this.map);
      this.sidebar = L.Control.Sidebar("sidebar").addTo(this.map);
    },
  },
};
</script>

<style>
#map {
  height: 600px;
}
</style>

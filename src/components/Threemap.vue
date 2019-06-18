<template>
  <div id="map"></div>
</template>

<script>
import * as THREE from "three";

export default {
  name: "ThreeMap",
  data() {
    return {
      scene: null,
      camera: null,
      light: null,
      cube: null,
      renderer: null,
      container: null
    };
  },
  created() {
    this.scene = new THREE.Scene();
    this.camera = new THREE.PerspectiveCamera(
      75,
      window.innerWidth / window.innerHeight,
      0.1,
      1000
    );
    this.renderer = new THREE.WebGLRenderer({
      alpha: true
    });
    this.renderer.setSize(window.innerWidth, window.innerHeight);
  },
  mounted() {
    this.container = document.getElementById("map");
    this.container.appendChild(this.renderer.domElement);
    this.init();
  },
  methods: {
    init() {
      console.log(window.innerWidth, window.innerHeight);
      var geometry = new THREE.BoxGeometry(1, 1, 1);
      var mat = new THREE.MeshBasicMaterial({ color: 0x00ffff });
      var cube = new THREE.Mesh(geometry, mat);
      this.scene.add(cube);
      this.camera.position.z = 5;
      this.render();
    },
    render() {
      requestAnimationFrame(this.render);
      this.renderer.render(this.scene, this.camera);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#map {
  border: 1px dashed orange;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

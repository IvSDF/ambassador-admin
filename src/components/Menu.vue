<template>
  <nav id="sidebarMenu" class="col-md-3 col-lg-2 d-md-block bg-light sidebar collapse">
    <div class="position-sticky pt-3">
      <ul class="nav flex-column">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">
            <span data-feather="home"></span>
            Dashboard
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script lang="ts">
import {Vue, Component} from 'vue-property-decorator';
import Nav from "@/components/Nav.vue";

@Component({
  components: {Nav}
})
export default class Menu extends Vue {

}
</script>

<style scoped>

</style>
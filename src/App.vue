

<template>
<v-app>
  	<v-toolbar app absolute class="elevation-0" color="transparent">
		<v-toolbar-title>
			<img :src="logo" alt="Code Hope" width="100px">
		</v-toolbar-title>
		<v-spacer></v-spacer>
		<v-btn outline color="cyan">WHAT WE DO</v-btn>
		<v-btn outline color="cyan">NEWS & BLOG</v-btn>
		<v-btn href="mailto:e.odunlade@devsdistrictnigeria.com?subject=Hinge Systems Inquiry"  depressed color="orange darken-3">CONTACT US</v-btn>
	</v-toolbar>
  <v-content>
    <router-view>

    </router-view>
  </v-content>
</v-app>

</template>

<script>
import logo from "@/assets/logo.png";

export default {
  name: "Hinge",
  data() {
    return {
      logo
    };
  }
};
</script>

<style>
</style>


<template>
  <v-app light>
    <side-bar v-if="showSideBar" />
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
import Sidebar from "~/components/SideBar.vue"
export default {
	name: "DefaultLayout",
	components: {
		"side-bar": Sidebar,
	},
	data() {
		return {}
	},
	computed: {
		showSideBar() {
			if (this.$route.path !== "/login") {
				return true
			}
			return false
		},
	},
}
</script>

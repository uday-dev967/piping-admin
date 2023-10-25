<template>
	<v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" fixed app>
		<v-list>
			<v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
				<v-list-item-action>
					<v-icon>{{ item.icon }}</v-icon>
				</v-list-item-action>
				<v-list-item-content>
					<v-list-item-title>{{ item.title }}</v-list-item-title>
				</v-list-item-content>
			</v-list-item>
		</v-list>
	</v-navigation-drawer>
</template>

<script>
export default {
	name: "SideBar",
	data() {
		return {
			clipped: false,
			drawer: true,
			items: [
				{
					icon: "mdi-home",
					title: "Home",
					to: "/",
				},
				{
					icon: "mdi-products",
					title: "Prouduct Details",
					to: "/create",
				},
				{
					icon: "mdi-manufaturers",
					title: "Manufratures",
					to: "/create",
				},
			],
			miniVariant: false,
		}
	},
	methods: {
		toggleMiniVariant() {
			if (this.miniVariant) this.miniVariant = false
			else this.miniVariant = true
		},
	},
}
</script>

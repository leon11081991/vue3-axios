<script setup lang="ts">
import axios from "axios";
import { onMounted, reactive } from "vue";

const emp = reactive({
	id: 0,
	name: "",
	createdAt: "",
	avatar: "",
});

onMounted(() => {
	axios({
		method: "get",
		url: "https://6684114f56e7503d1adf37a4.mockapi.io/api/v1/users",
	}).then((res) => {
		emp.id = res.data[0].id;
		emp.name = res.data[0].name;
		emp.createdAt = res.data[0].createdAt;
		emp.avatar = res.data[0].avatar;
	});
});
</script>

<template>
	<div class="greetings">{{ emp }}</div>
</template>

<style scoped></style>

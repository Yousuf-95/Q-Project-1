<script setup>
import { onMounted } from 'vue'
import { initDropdowns } from 'flowbite'
const { app, Realm } = useMyRealmApp();

onMounted(() => {
	initDropdowns();
})


const logout = () => {
    app.currentUser.logOut();
    navigateTo("/");
};

const name = ref(null);
const bankName = ref(null);
const invoiceName = ref(null);
const agencyName = ref(null);
const commissionPercentage = ref(null);
const maxCommissionPerWeek = ref(null);
const VATRegistered = ref(null);
const email = ref(null);
const password = ref(null);

const clickk = () =>{
	console.log(VATRegistered.value)
	// console.log(VATRegistered.value)
}

</script>

<template>
	<section>
		<nav class="bg-white border-gray-200 shadow-lg">
			<div class=" flex flex-wrap items-center justify-between py-4 w-11/12 mx-auto">
				<a href="#" class="flex items-center">
					<p class="text-xl font-bold">App Name</p>
				</a>
				<div class="flex items-center md:order-2 pr-2">
					<button type="button"
						class="flex mr-3 text-sm bg-gray-800 rounded-full md:mr-0 focus:ring-4 focus:ring-gray-300"
						id="user-menu-button" aria-expanded="false" data-dropdown-toggle="user-dropdown"
						data-dropdown-placement="bottom">
						<span class="sr-only">Open user menu</span>
						<img class="w-8 h-8 rounded-full" :src="curUserData?.user_info?.picture" crossorigin="anonymous"
							alt="user photo">
					</button>
					<!-- Dropdown menu -->
					<div class="z-50 hidden my-4 text-base list-none bg-white divide-y divide-gray-100 rounded-lg shadow"
						id="user-dropdown">
						<div class="px-4 py-3">
							<span class="block text-sm text-gray-900 ">Admin</span>
							<span class="block text-sm  text-gray-500 truncate">admin@gmail.com</span>
						</div>
						<ul class="py-2" aria-labelledby="user-menu-button">
							<li>
								<a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Dashboard</a>
							</li>
							<li>
								<a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Settings</a>
							</li>
							<li>
								<a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Earnings</a>
							</li>
							<li>
								<p href="#" @click="logout"
									class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 cursor-pointer">Sign
									out</p>
							</li>
						</ul>
					</div>
				</div>
				<div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="mobile-menu-2">
					<ul
						class="flex flex-col font-medium p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white">
						<li>
							<a href="#"
								class="block py-2 pl-3 pr-4 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0"
								aria-current="page">Home</a>
						</li>
						<li>
							<a href="#"
								class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">About</a>
						</li>
						<li>
							<a href="#"
								class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">Services</a>
						</li>
						<li>
							<a href="#"
								class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">Pricing</a>
						</li>
						<li>
							<a href="#"
								class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-blue-700 md:p-0 ">Contact</a>
						</li>
					</ul>
				</div>
			</div>
		</nav>
	</section>
	<section class="md:w-6/12 w-11/12 mx-auto my-5 border-2 p-5 rounded-md">
		<form @submit.prevent="clickk">
			<div class="grid gap-6 mb-6 md:grid-cols-2">
				<div>
					<label for="name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">
						Name</label>
					<input v-model="name" type="text" id="name"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="Abdullah" required>
				</div>
				<div>
					<label for="bankName" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">
						Name in bank account</label>
					<input v-model="bankName" type="text" id="bankName"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="Abdullah Al Mubin" required>
				</div>
				<div>
					<label for="invoiceName" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Name in
						invoice</label>
					<input v-model="invoiceName" type="text" id="invoiceName"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="Mubin" required>
				</div>
				<div>
					<label for="agencyName" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Agency name
					</label>
					<input v-model="agencyName" type="name" id="agencyName"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="Qualyval" required>
				</div>
				<div>
					<label for="commissionPercentage"
						class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Commission percentage</label>
					<input v-model="commissionPercentage" type="number" id="commissionPercentage"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="0.7" pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}" required>
				</div>
				<div>
					<label for="maxCommissionPerWeek"
						class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Max Commission Per Week</label>
					<input v-model="maxCommissionPerWeek" type="number" id="maxCommissionPerWeek"
						class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
						placeholder="57" required>
				</div>
				<div>
					<label for="VATRegistered" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Is VAT registered?</label>
					<ul class="grid w-full gap-6 grid-cols-2" id="VATRegistered">
						<li>
							<input v-model="VATRegistered" type="radio" id="yse" name="vat" value="yse" class="hidden peer"
								required>
							<label for="yse"
								class="inline-flex items-center justify-between w-full p-1.5 text-gray-500 bg-white border border-gray-200 rounded-lg cursor-pointer dark:hover:text-gray-300 dark:border-gray-700 dark:peer-checked:text-blue-500 peer-checked:border-blue-600 peer-checked:text-blue-600 hover:text-gray-600 hover:bg-gray-100 dark:text-gray-400 dark:bg-gray-800 dark:hover:bg-gray-700">
								<div class="block">
									<div class="w-full text-lg font-semibold">Yes</div>
								</div>
							</label>
						</li>
						<li>
							<input v-model="VATRegistered" type="radio" id="no" name="vat" value="no" class="hidden peer">
							<label for="no"
								class="inline-flex items-center justify-between w-full p-1.5 text-gray-500 bg-white border border-gray-200 rounded-lg cursor-pointer dark:hover:text-gray-300 dark:border-gray-700 dark:peer-checked:text-blue-500 peer-checked:border-blue-600 peer-checked:text-blue-600 hover:text-gray-600 hover:bg-gray-100 dark:text-gray-400 dark:bg-gray-800 dark:hover:bg-gray-700">
								<div class="block">
									<div class="w-full text-lg font-semibold">No</div>
								</div>
							</label>
						</li>
					</ul>
				</div>
			</div>
			<div class="mb-6">
				<label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Email
					address</label>
				<input v-model="email" type="email" id="email"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
					placeholder="john.doe@company.com" required>
			</div>
			<div class="mb-6">
				<label for="password" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Password</label>
				<input v-model="password" type="password" id="password"
					class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
					placeholder="•••••••••" required>
			</div>
			<div class="flex items-start mb-6">
				<div class="flex items-center h-5">
					<input id="remember" type="checkbox" value=""
						class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-blue-600 dark:ring-offset-gray-800"
						required>
				</div>
				<label for="remember" class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">I agree with the <a
						href="#" class="text-blue-600 hover:underline dark:text-blue-500">terms and conditions</a>.</label>
			</div>
			<button type="submit"
				class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Submit</button>
		</form>
	</section>
</template>
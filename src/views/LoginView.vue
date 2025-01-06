<script setup>
import axios from 'axios';
import { ref } from 'vue';


const client_id = import.meta.env.VITE_CLIENT_ID
const github_base_url = import.meta.env.VITE_GITHUB_OAUTH_URL
const github_url = import.meta.env.VITE_GITHUB_OAUTH_URL + '?client_id=' + client_id + '&scope=user'

function redirectToGithub() {
    window.location.href = github_url
}

</script>

<template>
    <div>
        <h1>LoginView</h1>
        <p>redirect to Github</p>
    </div>
    <div>
        <button @click="redirectToGithub">Login with Github</button>
    </div>

</template>

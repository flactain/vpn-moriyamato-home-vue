<script setup>
import axios from 'axios';
import { ref } from 'vue';


const client_id = import.meta.env.VITE_CLIENT_ID
const github_base_url = import.meta.env.VITE_GITHUB_OAUTH_URL
const github_url = import.meta.env.VITE_GITHUB_OAUTH_URL + '?client_id=' + client_id + '&scope=user'

async function getGitHubId() {
    await axios.get(github_base_url, {
        params: {
            client_id: client_id,
            redirect_uri: 'http://localhost:5173/',
            scope: 'user'
        }
    }).then(function (response) {
        console.log(response);

    }).catch(function (error) {
        console.log(error);

    })
}
</script>

<template>
    <div>

        <h1>you must login</h1>
    </div>
    <div>
        <a :href="github_url">loooogin</a>
    </div>
</template>

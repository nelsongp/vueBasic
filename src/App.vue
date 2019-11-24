<template>
    <div id="app">
        <h1>Vue Forms</h1>
        <h2>Publish a new status:</h2>
        <form class="new-status form-group" v-on:submit="publish">
            <label class="form-label">Your message:</label>
            <textarea v-model="currentStatus.text" 
            class="form-input" 
            placeholder="What's on your mind?">
            </textarea>
        </form>

    </div>
</template>
<script>
export default {
    
}
</script>
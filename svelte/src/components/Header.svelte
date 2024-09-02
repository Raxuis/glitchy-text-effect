<script>
    const inputChange = (e) => {
        console.log(e.target.value);
    };
</script>

<header>
    <h1 class="title">Glitch text effect !</h1>
    <p>Hover over the text to see the effect</p>

    <h2 class="title">Settings</h2>
    <div class="settings">
        <label for="glitch-frequency">Glitch frequency</label>
        <input
            type="range"
            id="glitch-frequency"
            min="0"
            max="1"
            step="0.01"
            value="0.7"
            on:input={(e) => inputChange(e)}
        />
        <output>0.7</output>
    </div>
</header>

<style>
    .settings {
        display: flex;
        align-items: center;
        gap: 1rem;
    }
</style>

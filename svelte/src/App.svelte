<script>
    import CustomText from "./components/CustomText.svelte";
    import Header from "./components/Header.svelte";
    import Input from "./components/Input.svelte";
    let inputText = "Hover me !";
    let glitchFrequency = 0.7;
</script>

<main class="center">
    <Header bind:glitchFrequency />
    <Input bind:inputText />
    <CustomText bind:textInput={inputText} />
</main>

<style>
    .center {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>

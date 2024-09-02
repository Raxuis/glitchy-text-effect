<script>
    import CustomText from "./components/CustomText.svelte";
    import Header from "./components/Header.svelte";
    import Input from "./components/Input.svelte";
    let inputText = "Hover me !";
</script>

<main class="center">
    <Header />
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

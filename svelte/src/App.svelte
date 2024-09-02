<script>
    import CustomText from "./components/CustomText.svelte";
    import Header from "./components/Header.svelte";
    import Input from "./components/Input.svelte";
</script>

<main class="center">
    <Header />
    <Input />
    <CustomText />
</main>

<style>
    .center {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>

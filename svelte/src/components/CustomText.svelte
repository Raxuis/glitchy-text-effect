<script lang="ts">
    import { onMount } from "svelte";
    export let textInput: string;
    let glitchChars = ["!", "@", "#", "$", "%", "?", "&", "*"];
    let defaultText = textInput;
    let interval: number;

    // Reactive statement to update defaultText whenever textInput changes
    $: defaultText = textInput;

    const applyGlitchEffect = (element: HTMLElement) => {
        element.addEventListener("mouseenter", () => {
            const originalText = defaultText;
            interval = setInterval(() => {
                const chars = originalText.split("");
                const glitchFrequency = (
                    document.querySelector(
                        "#glitch-frequency"
                    ) as HTMLInputElement
                ).value;
                const isGlitched = Math.random() < parseFloat(glitchFrequency);

                const glitched = chars.map((char) => {
                    const randGlitchChar =
                        glitchChars[
                            Math.floor(Math.random() * glitchChars.length)
                        ];
                    return Math.random() < 0.5 ? char : randGlitchChar;
                });

                element.textContent = isGlitched
                    ? glitched.join("")
                    : originalText;
            }, 110);
        });

        element.addEventListener("mouseleave", () => {
            clearInterval(interval);
            element.textContent = defaultText;
        });
    };

    onMount(() => {
        const element = document.querySelector(".glitch");
        applyGlitchEffect(element);
    });
</script>

<p class="glitch">{textInput}</p>

<style>
    .glitch {
        font-family: "Courier New", Courier, monospace;
        text-shadow: 0 0 10px #00f;
        font-size: 2rem;
    }
</style>

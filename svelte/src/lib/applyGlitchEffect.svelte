<script>
    let defaultText = textInput.value || hoverText;
    const applyGlitchEffect = (element) => {
        let interval;
        element.addEventListener("mouseenter", () => {
            const originalText = defaultText;
            interval = setInterval(() => {
                const chars = originalText.split("");
                const glitchFrequency =
                    document.querySelector("#glitch-frequency").value;
                const isGlitched = Math.random() < glitchFrequency;

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
</script>

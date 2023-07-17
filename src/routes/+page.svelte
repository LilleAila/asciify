<script lang="ts">
    // Numbers: () | */_ } <|  _\* /(noe idk) */ {-} °/

    const ascii: { [key: string]: string } = {
        A: `/-\\`,
        B: `|3`,
        C: `\(`,
        D: `|)`,
        E: `|=`,
        F: `/=`,
        G: `(=`,
        H: `|-|`,
        I: `|`,
        J: `\_|`,
        K: `|<`,
        L: `|\_`,
        M: `|\\/|`,
        N: `|\\|`,
        O: `\()`,
        P: `|°`,
        Q: `().`,
        R: `|°\\`,
        S: `\_\\-`,
        T: `-|-`,
        U: `|\_|`,
        V: `\\/`,
        W: `\\/\\/`,
        X: `><`,
        Y: `\\|/`,
        Z: `-/_`,
        Æ: `/|=`,
        Ø: `(/)`,
        Å: `/°\\`,

        "0": "()",
        "1": "|",
        "2": "*/_",
        "3": "}",
        "4": "<|",
        "5": "_\\*",
        "6": "/.",
        "7": "*/",
        "8": "{-}",
        "9": "°/"
    }
    let input = ""
    $: asciified = input.toUpperCase().replace(new RegExp(Object.keys(ascii).join('|'), 'g'), (match) => ascii[match]);
    $: asciified_escaped = asciified.replace(/[\\_()*|]/g, '\\$&');
</script>

<main class="w-full text-center flex justify-center">
    <div class="flex flex-col justify-center w-4/5 p-8">
        <h2 class="text-4xl my-2">
            ASCIIfy text - /-\ _\- ( | |
        </h2>
        <input
            type="text"
            placeholder="Input"
            class="input w-full my-2"
            bind:value={input}
        />
        <p class="text-3xl text-primary break-all my-2">{asciified}</p>
        {#if asciified.length > 0}
            <p class="text-sm">Discord-compatible:</p>
        {/if}
        <p class="text-lg text-secondary break-all my-2">{asciified_escaped}</p>
    </div>
</main>
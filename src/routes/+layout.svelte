<script>
	import ipLogo from "$lib/assets/ip-address.png"
</script>

<svelte:head>
	<link rel="icon" href={ipLogo} />
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>IP Address Tracker</title>
</svelte:head>

<slot />

<style>
    :root {
        font-family: Arial, sans-serif;
        text-align: center;
        background: linear-gradient(to right, #173997, #00ff44);
        color: white;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    ::selection {
        background: #00ffff;
        color: black;
    }

    @media (prefers-color-scheme: dark) {
        :root {
            background: linear-gradient(to right, #001f3f, #007700);
            color: white;
        }

        ::selection {
            background: white;
            color: black;
        }
    }
</style>

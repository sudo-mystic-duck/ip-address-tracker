<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IP Address Tracker</title>
<h1>Your IP Address is:</h1>
<h2>{ip}</h2>
<a href="/privacy-policy">
    <img src={privacyLogo} alt="privacy-policy" />
</a>

<script>
    import privacyLogo from "$lib/assets/privacy-policy.png"

    let ip = "Loading...";
    async function fetchIP() {
        try {
            const response = await fetch("/api/ip");
            const data = await response.json();
            ip = data.ip;
        } catch (error) {
            ip = "Error fetching IP";
        }
    }
    fetchIP();
</script>

<style>
  h1 {
    font-size: 3em;
    margin-bottom: 0.5em;
  }

  h2 {
    font-size: 1.5em;
    border: 0.2cm solid white;
    border-radius: 10px 10px 10px 10px;
    background-color: white;
    color: black;
    box-shadow: -0.5em 0px 0.5em rgba(0,0,0,0.5);
  }

  img {
      position: fixed;
      width: 3em;
      height: 3em;
      bottom: 2em;
      right: 1em;
  }

  @media (max-width: 700px) {
    h1 {
      font-size: 1.75em;
    }

    h2 {
      font-size: 1.1em;
      padding: 0.5em;
    }
  }

  @media (prefers-color-scheme: dark) {
    h2 {
      background-color: black;
      color: white;
      border-color: black;
      box-shadow: -0.5em 0px 0.5em rgba(255, 255, 255, 0.5);
      text-shadow: 0 0 0.5em #00ffff, 0 0 0.5em #00ffff, 0 0 0.5em #00ffff, 0 0 0.5em #00ffff;
    }
  }
</style>

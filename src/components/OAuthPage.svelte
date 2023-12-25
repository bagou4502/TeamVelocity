<script>
    import { onMount } from 'svelte';
    import { navigate } from 'svelte-routing';

    onMount(() => {
        const clientId = 'VotreClientIDAzure';
        const redirectUri = encodeURIComponent('http://localhost:5000/oauth-callback');
        const scope = encodeURIComponent('user.read mail.read');
        const authUrl = `https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=${clientId}&response_type=code&redirect_uri=${redirectUri}&scope=${scope}&response_mode=query`;

        window.location.href = authUrl;
    });
</script>

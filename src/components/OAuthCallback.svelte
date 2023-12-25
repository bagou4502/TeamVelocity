<script>
    import { onMount } from 'svelte';
    import { invoke } from '@tauri-apps/api/tauri';

    onMount(async () => {
        const urlParams = new URLSearchParams(window.location.search);
        const code = urlParams.get('code');

        if (code) {
            try {
                await invoke('exchange_code_for_token', { code });
                // Rediriger vers la page d'accueil ou une autre page après l'authentification
            } catch (error) {
                console.error('Erreur lors de l\'échange du code :', error);
            }
        }
    });
</script>

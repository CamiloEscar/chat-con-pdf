<script>
    import { Alert } from 'flowbite-svelte';
    import {APP_STATUS, appStatus} from '../pages/store'
  import StepUpload from './StepUpload.svelte';
  import StepLoading from './StepLoading.svelte';
  import StepChat from './StepChat.svelte';
  </script>

{#if $appStatus === APP_STATUS.INIT}
<StepUpload />
{:else if $appStatus === APP_STATUS.LOADING}
<StepLoading/>

{:else if $appStatus === APP_STATUS.ERROR}
<Alert>
    <span class="font-medium">algo malo paso!</span>
    hay un error en la aplicacion
</Alert>
{:else if $appStatus === APP_STATUS.CHAT_MODE}
<StepChat />
{:else}
<Alert>
    <span class="font-medium">accion no reconocida</span>
    este estado de la aplicacion no esta reconocida
</Alert>
{/if}


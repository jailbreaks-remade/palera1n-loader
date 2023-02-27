<script lang="ts">
    export let func: any;
    export let style: any;
</script>

<div style={style} class="button-box">
    <div class="settings">
        <span class="text"></span>
    </div>
    <div on:click={func} class="install">
      <span class="text">Install</span>
    </div>
    <div class="info">
        <span class="text"></span>
    </div>
</div>
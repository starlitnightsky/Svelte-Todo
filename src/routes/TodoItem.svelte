<script>
    export let completed;
    export let text;
</script>

<div>
    <input type="checkbox" checked={completed}/> 
    { text }
</div>
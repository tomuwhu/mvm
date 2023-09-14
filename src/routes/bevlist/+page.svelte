<script>
    var t = [], s = ''
</script>
<h1 align="center">Bevásárlólista</h1>
<div>
<input type="text" bind:value={s} on:change={() => {
    t.push(s)
    t = t
    s = ''
}}>
</div>
<hr>
{#each t as e, i}
    <div class={i % 2 ? 'e' : 'x'}>{e}</div>
{/each}

<style>
    div {
        padding: 10px;
        text-align: center;
    }
    div.e {
        background-color: aquamarine;
    }
</style>
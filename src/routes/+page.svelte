<script>
    var i1 = "Cica"
</script>
<h1 align="center">Cica</h1>
<form align="center">
    <input class="form-control" type="text" bind:value={i1}>
</form>

<h1 align="center">
    {i1.split("").reverse().join("")}
</h1>

<a href="calc">Számológép</a>
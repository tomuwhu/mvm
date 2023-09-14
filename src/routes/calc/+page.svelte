<script>
    const g = ["123/C","456*√","789-=","0.%+"]
    const f = e => {
        if ((i==0 || laste) && e != '=') {
            i = ''
            laste = false
        }
        if (e == "=") {
            i = eval(s+i)
            laste = true
            s = ''
        } else if ('+-*/'.includes(e)) {
            s = i + e
            laste = true
        } else if (e == 'C') {
            i = '0'
        } else if (e == '%') {
            i = i / 100
        } else if (e == '√') {
            i = Math.sqrt(i)
        } else {
            i += e
        }
    }
    var i = 0, laste = false, s = ''
</script>
<br><br>
<h1 align="center">Számológép</h1>
<br>
<table>
    <tr><td colspan="5"><input class="form-control i" bind:value={i}></td></tr>
    {#each g as i}
    <tr>
        {#each i as e}
            <td rowspan={e == '=' ? 2 : 1}><button 
                class="btn btn-primary x {e == '=' ? 'eg' : ''}" 
                on:click={() => f(e)}>{e}</button></td>
        {/each}
    </tr>
    {/each}
</table>
<style>
@import url('https://fonts.googleapis.com/css2?family=Rubik+Mono+One&display=swap');
* {
    font-family: 'Rubik Mono One', sans-serif;
}
table {
    margin: auto;
}
button.x {
    width: 60px;
    font-size: 25px;
}
button.eg {
    height: 105px;
}
.i {
    text-align: right;
    font-size: 25px;
    width: 300px;
    margin: auto;
}
td {
    text-align: center;
}
</style>
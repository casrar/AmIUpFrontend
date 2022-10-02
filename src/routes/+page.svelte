<script>
let up = true
let buttonText = 'Am I up?'
const determine = () => {
    return Math.random()
}

const changeText = () => {
    if (determine() > 0.5) {
        up = true
        buttonText = 'You are up!'
    } else {
        up = false
        buttonText = 'You are down!'
    }
}
</script>

<div class="vertical-center">
{#if up}
    <button on:click="{changeText}" class="button buttonUp">{buttonText}</button>
{:else}
    <button on:click="{changeText}" class="button buttonDown">{buttonText}</button>
{/if}
</div>

<style>
    .vertical-center {
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    }
    .button {
        display: inline-block;
        border-radius: 10px;
        border: 4px double #cccccc;
        color: #eeeeee;
        text-align: center;
        vertical-align: center;
        font-size: 28px;
        padding: 20px;
        height: 200;
        width: 400px;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
        -o-transition: all 0.5s;
        transition: all 0.5s;
        cursor: pointer;
        margin: 5px;
      }

    .buttonUp {
        background-color: green;
    }

    .buttonDown {
        background-color: red;
    }
</style>
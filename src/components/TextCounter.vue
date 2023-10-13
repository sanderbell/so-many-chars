<template>
    <p id="count">
        <span class="digit">{{ text.replace(/[\n]/g, '').length }}</span>
        {{ text.replace(/[\n]/g, '').length === 1 ? 'character' : 'characters'
        }} &nbsp;
        <span class="digit">{{ text.replace(/[\s\n]/g, '').length }}</span>
        {{ text.replace(/[\s\n]/g, '').length === 1 ? 'character' : 'characters'
        }} excl. spaces &nbsp;
        <span class="digit">{{ text.split(/[\p{L}0-9_-]+/u).length - 1 }}</span>
        {{ (text.split(/[\p{L}0-9_-]+/u).length - 1 === 1) ? 'word' : 'words' }}
    </p>
    <div id="text-container">
        <textarea id="text" v-model="text" placeholder="Paste your text here..."></textarea>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            text: '',
        };
    },
};  </script>
  
<style >
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans&family=Nunito:wght@300;500&display=swap');



html {
    box-sizing: border-box;
    font-family: 'Nunito', sans-serif;
    height: 100%;
    margin: 0;
    overflow: hidden;
    padding: 0;
    width: 100%;
}

body {
    align-items: center;
    background-color: rgb(234, 249, 226);
    color: #797979;
    display: flex;
    height: 100%;
    justify-content: center;
    text-align: center;
    width: 100%;
}

*,
*::before,
*::after {
    /* border: 1px solid #b46565; */
    box-sizing: inherit;
    margin: 0;
    padding: 0;
    user-select: none;
}

#app {
    align-items: center;
    display: flex;
    flex-direction: column;
    height: 80%;
    justify-content: center;
    width: 90%;
    user-select: none;
}

#count {
    font-size: 1.6em;
    padding-bottom: 3.4em;
}

.digit {
    background-color: #839075ec;
    border-radius: 0.7em;
    color: #fff;
    padding: 0.15em 0.45em;

}

#text-container {
    height: 100%;
    width: 85%;
}

#text {
    border: none;
    border-radius: 1em;
    /* box-shadow: 0px 0px 3em #c4c4c476; */
    color: #797979;
    font-family: 'Nunito', sans-serif;
    height: 85%;
    line-height: 1.35em;
    outline: none;
    padding: 1.4em;
    resize: none;
    transition: box-shadow 1.3s;
    width: 100%;
    /* border: 1px dotted #cbcbcb; */
}

#text:focus,
#text:focus-visible {
    box-shadow: 0px 0px 4em #a7b69693;
}

#text::placeholder {
    opacity: 0.3;
}

#mobile-warning {
    display: none;
}

@media (max-width: 800px) {
    #mobile-warning {
        display: block;
        font-size: 1.5em;
    }

    #count,
    #text-container {
        display: none;
    }
}
</style>
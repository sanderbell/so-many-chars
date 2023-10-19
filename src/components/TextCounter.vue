<template>
    <p id="count">
        <span class="digit">{{ text.replace(/[\n]/g, '').length }}</span>
        {{ text.replace(/[\n]/g, '').length === 1 ? 'character' : 'characters'
        }} &nbsp;
        <span class="digit">{{ text.replace(/[\s\n]/g, '').length }}</span>
        {{ text.replace(/[\s\n]/g, '').length === 1 ? 'character' : 'characters'
        }} excluding spaces &nbsp;
        <span class="digit">{{ text.split(/[\p{L}0-9_-]+/u).length - 1 }}</span>
        {{ (text.split(/[\p{L}0-9_-]+/u).length - 1 === 1) ? 'word' : 'words' }}
    </p>
    <div id="text-container">
        <textarea autofocus id="text" v-model="text" placeholder="Paste your text here..."></textarea>
    </div>
    <footer>
        © 2023
        <a target="_blank" href="https://sanderbell.dev">Sander Bell</a>

    </footer>
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
    background-color: #def4d2c5;
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
    font-size: 1.7em;
    padding-bottom: 3.3em;
}

.digit {
    background-color: #839075b6;
    border-radius: 0.5em;
    color: #fff;
    padding: 0.15em 0.45em;
    font-weight: bold;
}

#text-container {
    height: 100%;
    width: 85%;
}

#text {
    border: none;
    border-radius: 1em;
    color: #797979;
    font-family: 'Nunito', sans-serif;
    height: 85%;
    line-height: 1.35em;
    outline: none;
    padding: 1.4em;
    resize: none;
    transition: box-shadow 1.3s;
    width: 100%;
    font-size: 1.1rem;
    box-shadow: 0px 0px 1.5em #cfd8c693;

}

#text:focus,
#text:focus-visible {
    box-shadow: 0px 0px 4.5em #a7b69693;
}

#text::placeholder {
    opacity: 0.3;
}

#text::selection {
    background: #def4d2c5;
}

#mobile-warning {
    display: none;
}


a {
    border-bottom: 0.1em solid #839075b6;
    color: #839075b6;
    text-decoration: none;
}



footer {
    font-size: 0.9rem;
    bottom: 2rem;
    color: #839075b6;
    left: 50%;
    position: absolute;
    text-align: center;
    transform: translateX(-50%);
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
<template>
<div class="app">
<Header title="The Anime Quoter" />
<Quote :quote="quote" />
</div>

</template>

<script>
export default {
    data() {
        return {
            quote: {
                content: 'Content goes here',
                anime: 'Naruto',
                character: 'Madara'
            },
            quotes: []
        }
    },
    methods: {
       getQuote() {
      const data =  fetch('https://animechan.vercel.app/api/random')
        .then(res => res.json());
         console.log(data);
      

          //this.quote = {
           // content: data.quote,
           // anime: data.anime,
           // character: data.character
        //}
      },
    created () {
        this.getQuote();
    }
    }
}
</script>

<style lang="scss">
:root {
--primary: #D81E5B;
--secondary: #8A4FFF;
--tertiary: #32CBFF;
--dark: #1d2a41;
--light: #eee;
--grey: #848484;
}

* {
margin:0;
padding:0;
box-sizing: border-box;
font-family: 'Fira Sans', sans-serif;
}
</style>

<template>
<div class="app">
<Header title="The Anime Quoter" />
<Quote :quote="quote" />

<Footer />
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
      async fetchQuote() {
      const data = await fetch(
        'https://animechan.vercel.app/api/random'
      ).then(res => res.json())
         console.log(data);
         this.quote = {
         content: data.quote,
            anime: data.anime,
         character: data.character
        }
    }
},
    created () {
        this.fetchQuote();
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
.button {
margin-top:20px;
margin-left:-30px; 
}
.button #button {
   border-radius:20px; 
   padding: 10px 14px;
          font-size: 24px;
          font-weight: 600;
          color: var(--light);
          text-align:center;
    background: #ce19a1; 
    border-color: #ce19a1; 
     
}
</style>


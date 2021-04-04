<template>
    <div>
        <h1>
            <ul>
                <book-item v-for="book in books" :key="book" @addBook='appendBook' > </book-item>
            </ul>
        </h1>
        <hr>
        <book-form @addBook='appendBook'> </book-form>
    </div>
</template>
<script>
    import BookItem from './BookItem';
    import BookForm from './BookForm';
    export default{
        name: 'BookList',
        components:{
                BookItem,
                BookForm
        },
        data() {
            return{
                title :'All Books',
                books : [
                        {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                        {title: 'American Gods', author: 'Neil Gaiman'},
                        {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
                    ]
            };
        },
        methods:{
            appendBook(bookTitle, bookAuthor){
                this.books.push({ title: bookTitle, author: bookAuthor })
            }
        }
        
    };
</script>
<style scoped>
ul{
    list-style-type: none;
    padding : 0;
}
li{
    display: block;
    margin: 0 10px;
}
</style>
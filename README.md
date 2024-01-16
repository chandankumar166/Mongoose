# Mongoose

### Database Connection
```sh
mongoose.connect('mongodb://127.0.0.1:27017/db_name');
#Establishes a connection to database
```

### Defining Schema
```sh
const bookSchema = mongoose.Schema(
    {
        title: {
            type: String,
            required: true,
        },
        author: {
            type: String,
            required: true,
        },
        publishYear: {
            type: Number,
            required: true,
        }
    },
    {
        timestamps: true
    }
);
```
### Creating Model
```sh
const Book = mongoose.model('Book', bookSchema);
# It creates a model based on schema
```

## CRUD operations

### Appending a new document to the collection
```sh
const newBook = {
            title:'Rich Dad Poor Dad',
            author: 'Robert T. Kiyosaki',
            publishYear: 1997
        };
        const book = await Book.create(newBook);
```
### Searching using Mongoose
```sh
const books = await Book.find({});
# Returns all the rows in the database

const book = await Book.findById(id);
# Returns a book with specific id
```

### Modifications using Mongoose
```sh
const book = await Book.findByIdAndUpdate(id, updated_data);
# updates the data of a particular id
```

```sh
const book = await Book.findByIdAndDelete(id);
# Deletes a book with a particular id
```



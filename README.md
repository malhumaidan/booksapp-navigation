# booksapp-navigation

### Requirements
1-  Book class/object<br>
2-  Home page to display all the books<br>
3-  Detail page to navigate to and display book details<br>

## Step 1 (Book.dart)
#### Create Book class<br>
- In our flutter project, click on ```lib``` folder and create new file inside it and call it ```Book.dart```<br>

the result should be something like this👇
<br>
<br>
<img width="236" alt="Screen Shot 2023-06-21 at 11 51 58 AM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/5c0fb16a-9cd9-4c77-b100-1ed68f532b99">

- Now inside this newly created file, lets create the blueprint for our ```Book``` object with 3 required properties/fields.<br>
    name (string)<br>
    author (string)<br>
    imageUrl (string)<br>
<img width="640" alt="Screen Shot 2023-06-21 at 11 56 51 AM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/3d402d2c-b2cd-4c2e-a9e7-feb79bdfa1fc"> <br>

Comments: <br>
- Note that all the feilds has to be marked final.<br>
- We have to create a constructor (line 6) too and specify which fields are going to be required when calling this object, in our case, all the fields are required, so we added all of them inside the constructor.

## Step 2 (main.dart)
#### Step 2.1
-  Back to our ```main.dart``` file, lets delete everything we don't want such as theme and title from the ```MaterialApp()``` and the whole widget below, and set the ```MaterialApp()``` ```home:``` property to null.<br>

the result should be something like this👇
<br>
<br>
<img width="826" alt="Screen Shot 2023-06-21 at 1 03 54 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/76e7473d-72b1-4fe5-a102-8cd365e717ec">

#### Step 2.2
-  Copy and paste the list ```books``` I provided below the ```MaterialApp()``` widget.<br>

```dart
  List books = [
  Book(
    name: 'A Song of Ice and Fire',
    author: 'George R.R. Martin',
    imageUrl:
        'https://upload.wikimedia.org/wikipedia/en/d/dc/A_Song_of_Ice_and_Fire_book_collection_box_set_cover.jpg',
  ),
  Book(
    name: 'The Alchemist',
    author: 'Paulo Coelho',
    imageUrl:
        'https://images-na.ssl-images-amazon.com/images/S/compressed.photo.goodreads.com/books/1654371463i/18144590.jpg',
  ),
  Book(
    name: 'Who Moved My Cheese',
    author: 'Spencer Johnson',
    imageUrl: 'https://m.media-amazon.com/images/I/81GBTzGb+2L.jpg',
  ),
  Book(
    name: 'Sherlock Holmes',
    author: 'Sir Arthur Conan Doyle',
    imageUrl:
        'https://d28hgpri8am2if.cloudfront.net/book_images/onix/cvr9781607102113/the-adventures-of-sherlock-holmes-and-other-stories-9781607102113_hr.jpg',
  ),
];



```
<br>

the result should be something like this👇
<br>
<br>
<img width="532" alt="Screen Shot 2023-06-21 at 1 12 51 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/ff5f25a2-1c34-4e65-891c-425dbd059c68">

As we can see, there is an error saying that the object ```Book()``` is not defined, this means that we have to import it from our ```Book.dart``` file we created in step 1<br>
To solve this issue, CLICK on the word ```Book``` then click on the little yellow lamp and choose ```Import library 'Book.dart'```.<br>
look at the screenshot below👇
<br>
<br>
<img width="546" alt="Screen Shot 2023-06-21 at 1 10 53 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/05ea7ca3-96e2-4328-a0f7-fafe168348b4"> <br>
<br>
Now the ```Book``` object should be in green and an import statement has been added to the top if the ```main.dart``` file automatically.
look at the screenshot below👇
<br>
<br>
<img width="731" alt="Screen Shot 2023-06-21 at 1 30 44 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/64220cf2-cd4a-4c52-8323-0f8c2da5a2e6"><br>

#### Step 2.3
- Now we create the home page to display all our books.<br>
- Lets create it above the list we just cerated.<br>

To avoid errors, type ```st``` and wait for the menu to appear and choose ```Flutter Stateless Widget```👇
<br>
<br>
<img width="722" alt="Screen Shot 2023-06-21 at 1 41 06 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/20917ff9-fa77-466f-b061-58accecd5b3a"><br>

🪄 Wow, a new widget called ```MyWidget``` appeared out of no where👇.<br>
<br>
<img width="667" alt="Screen Shot 2023-06-21 at 1 45 47 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/6f3bd2b5-5342-4d62-8071-da519b4e3531">
<br>
<br>
Lets change its name from ```MyWidget``` to ```BooksHomePage``` and use it in ```MaterialApp()``` ```Home``` property👇.
<br>
<br>
<img width="722" alt="Screen Shot 2023-06-21 at 1 49 21 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/68e69272-3146-4c9a-8b3a-540f583a218c">
<br>

#### Step 2.4
- Now lets edit our `BooksHomePage` widget and make it return/display our books from the list we created below.<br>

First, Lets replace `const PlaceHolder()` with a `Scaffold()` widget and give it an appbar with the title `Books` (be carful with the brackets, commas, etc...)👇.<br>

<img width="585" alt="Screen Shot 2023-06-21 at 2 05 27 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/0a855b1d-e7d8-41ef-962e-72345874d082"> <br>

- Now in the lets add a body and give it a ```ListView.builder()``` to create our list of books.<br>

Notes:<br>
In order to use the ```ListView.builder()``` widget, we need to give it two things.<br>
The first is ```itemCount``` which is how many items should it build?<br>
The second is ```itemBuilder``` which is what to build?<br>
Lets see this in action👇.<br>
<br>
<img width="623" alt="Screen Shot 2023-06-21 at 3 07 13 PM" src="https://github.com/malhumaidan/booksapp-navigation/assets/89436547/0c1417b3-ccd6-42e4-bd01-de407c9e3f19">
<br>
Lets review the code above:<br>
```itemCount``` takes a number so we will give it ```books.length``` which is a number.<br>
```itemBuilder``` takes a nameless/anonymous function with two parameters ```context``` and ```index``` so, the function should be like this```(context,index){}```.<br>
More on `ListView.builder()` can be found [here (flutter documentation)](https://api.flutter.dev/flutter/widgets/ListView-class.html#widgets.ListView.2) . <br>

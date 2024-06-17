# Praca Inżynierska: Księgarnia Internetowa z Elementami AI / Engineering Thesis: Online Bookstore with AI Elements

#### Uwaga! 
Ze względu na prawa autorskie i przepisy uczelniane, repozytorium nie zawiera plików z kodem źródłowym.

#### Note!
Due to copyright laws and university regulations, the repository does not contain source code files.

### Angielska wersja niżej / English description below

## PL: Opis pracy

Celem pracy było zaprojektowanie i zaimplementowanie księgarni internetowej umożliwiającej automatyczne generowanie opisów książek przez wykorzystanie sztucznej inteligencji. Dodatkowo imoplementacji funkcji sugerowania czytelnikowi kolejnych książek przez AI na podstawie jego historii zakupowej i jego opinii.

### Wykorzystane technologie
- php 8, Symfony 7, MySQL
- JavaScript, Stimulus
- Twig, Bootstrap, Tabler
- Symfony Messenger, Doctrine
- GPT API, Cloudinary cloud
- Docker, php Unit


Poniżej przedstawiona została strona główna serwisu.

![Strona główna serwisu](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/homepage.png)

Aplikacja udostępnia dla użytkowników katalog z książkami. Dostępne są opcje filtrowania, sortowania, dodania do koszyka oraz zakupu książek. Zaimplementowany został również mechanizm ocen książek w skali gwiazdkowej od 1 do 5 gwiazdek. Katalog księgarni wraz z alertem po dodaniu książki do koszyka ukazany został poniżej.

![Katalog księgarni](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/catalog.png)


Poniżej ukazana została strona ze szczegółami książki.

![Strona ze szczegółami książki](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/book_details.png)

Aplikacja udostępnia użytkownikom mechanizmy sztucznej inteligencji wspomagające korzystanie z serwisu. Pierwszą funkcjonalnością jest dostępna tylko dla administratorów funkcja generowania opisu książki. Użytkownik wprowadzając na strone edycji/dodawania książki tytuł oraz autora lub autorów książki, ma możliwość wygenerowania za pomocą modelu GPT opisu książki. Dodatkowo po wprowadzeniu opisu użytkownik ma możliwość skorzystania z drugiej opcji, a więc z przeredagowania opisu. Obie funkcjonalności w szybki sposób dostarczają kreatywny i spójny opis zaoszczędzając czas wprowadzenia nowej książki do księgarni.


Strona edycji książki wraz z wygenerowanym opisem przez model GPT przedstawiona została poniżej.

![Strona edycji książki](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/edit_book.png)


W systemie umieszczone również zostały help boxy pomagające użytkownikom korzystać z serwisu.

![Help box](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/edit_book_ai.png)


Ostatnim algorytmem bazującym na sztucznej inteligencji jest algorytm proponowania kolejnych książek do przeczytania. Wykonuje się on asynchronicznie w tle za pomocą kolejek Symfony Messenger w odpowiedzi na różne zdarzenia w systemie. Dzięki temu użytkownik ma możliwość otrzymania kolejnych propozycji do przeczytania prosto od modelu GPT. Dzięki
wykorzystaniu w algorytmie informacji na temat użytkownika, dla którego mają zostać
zaproponowane kolejne książki do przeczytania, algorytm odwołuje się do wystawionej
oceny dla książki, na bazie której mają zostać zwrócone zarekomendowane pozycje. Jeżeli
w systemie jest możliwa do wykorzystania informacja o ocenie, a więc jeżeli klient
zdecydował się na recenzję książki w skali gwiazdkowej od 1 do 5, algorytm wyśle różne
zapytania do modelu GPT. Dla czytelnika, który ocenił książkę niską lub średnią notą,
a więc ocena od 1 do 3 włącznie, algorytm w zapytaniu do sztucznej inteligencji umieści tę
informację, żądając zarekomendowania propozycji o innej tematyce lub stylistyce, tak aby
zminimalizować ryzyko zakupu książki przez czytelnika, która mogłaby ponownie nie
wpaść w jego gusta. Z kolei analogiczną sytuacją będzie sytuacja dla oceny
4 oraz 5 gwiazdek. Wtedy algorytm w zapytaniu będzie żądał od modelu, aby ten
proponował zbliżone tematyką kolejne książki do zakupu.


Strona profilu użytkownika wraz z zaproponowanymi książkami do przeczytania przez sztuczną inteligencje przedstawiona została poniżej.

![Rekomendacje AI](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/ai_recommendations.png)


Dla aplikacji zostały zaimplementowane również unit testy oraz wygenerowany został raport pokrycia kodu testami przy pomocy xDebug. Poniżej został przedstawiony raport pokrycia testami dla klasy serwisu OpenAIService.php


![Testy](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/tests.png)


## ENG: Thesis description 

The aim of the work was to design and implement an online bookstore enabling automatic generation of book descriptions by using artificial intelligence. Additionally, implementation of the function of suggesting further books to the reader by AI based on user purchasing history and opinions.


### Tech stack
- php 8, Symfony 7, MySQL
- JavaScript, Stimulus
- Twig, Bootstrap, Tabler
- Symfony Messenger, Doctrine
- GPT API, Cloudinary cloud
- Docker, php Unit


Below is the homepage of the service.

![Homepage](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/homepage.png)

The application provides users with a book catalog. Available options include filtering, sorting, adding to the cart, and purchasing books. A star rating system from 1 to 5 stars is also implemented. The bookstore catalog with an alert after adding a book to the cart is show below.

![Bookstore Catalog](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/catalog.png)

Below is the book details page.

![Book Details Page](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/book_details.png)

The application provides users with AI mechanisms to support the use of the service. The first functionality is a book description generation feature available only to administrators. By entering the title and author(s) on the book editing/adding page, the user can generate a book description using the GPT model. Additionally, after entering a description, the user can use the second option, which is to rephrase the description. Both functionalities quickly provide a creative and coherent description, saving time in adding a new book to the bookstore.

The book editing page with a description generated by the GPT model is shown below.

![Book Editing Page](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/edit_book.png)

Help boxes have also been placed in the system to assist users in using the service.

![Help Box](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/edit_book_ai.png)

The final AI-based algorithm is the recommendation algorithm for suggesting next books to read. It runs asynchronously in the background using Symfony Messenger queues in response to various system events. This way, the user can receive book recommendations directly from the GPT model. Using information about the user, the algorithm refers to the ratings given to books, based on which recommended titles are returned. If a star rating from 1 to 5 is available, the algorithm sends various queries to the GPT model. For a reader who rated a book with a low or average score (1 to 3 stars), the algorithm includes this information in the query, requesting recommendations of different themes or styles to minimize the risk of purchasing a book that might not appeal to them again. Similarly, for ratings of 4 and 5 stars, the algorithm requests the model to suggest books of similar themes for purchase.

The user's profile page with book recommendations suggested by the AI is show below.

![AI Recommendations](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/ai_recommendations.png)

Unit tests have also been implemented for the application, and a code coverage report was generated using xDebug. Below is the test coverage report for the OpenAIService.php service class.

![Tests](https://raw.githubusercontent.com/Patryk-Samulewicz/Online-Bookstore-AI-Engineering-Thesis/main/tests.png)

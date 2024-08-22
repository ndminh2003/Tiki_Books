# Tiki_Books
![Logo_Tiki](https://github.com/user-attachments/assets/f7ba23db-e674-46c5-bbc3-5020c759a3c3)
## Final Report on Tiki Book E-cormmerce | Presenter: Nguyen Dai Minh
### 1. Problem Statement
The primary objective of this report is to generate answers and recommendations for the following
questions:
* What kind of books is the most liked ?
* What authors is the most popular ?
* What are the best-seller books ?
* What publishers is the most popular ?
* Does the discount currently equals higher sales ?
* Does prices affect book sales ?
* Does the length of the books affect book sales ?
* Does the number of reviews affect book sales ?
* Does the average rating affect book sales ?
* Any recommendation to increase sales of books ?
* ...etc.
### 2. Data Description
The data is collected by scraping the Tiki E-commerce market and store in a csv file for usage
and data is also available for public usage on Kaggle. Let’s now understand the parameters of
the dataset collected:
* product_id: id of the product in the Tiki database (unique)
* title: name of the book, maybe contain republish time
* authors: same with it’s name
* original_price: price at the first time
* current_price: price at present if having a discount
* quantity: total number of books sold of all time
* category: kind of book
* n_review: number of reviews
* avg_rating: average rating (max 5.0)
* pages: total pages of each book
### 3. Data Cleaning and Manipulation
The dataset only contain 2000 rows representing 2000 books so i will be using Google Sheets to
do both data cleaning and manipulation:
1. Clear format, highlight and color headers, freeze headers for easy views, left alignment.
2. Conditional formatting to identify missing values (Around 20% of the value is missing)
3. Replace missing values with an "Unknown" value for text and use average imputations for
numeric value
4. Generate new columns for discount
5. Transfer some of the author name in title to the authors columns and replacing the "un-
known" values
6. Compare category and title columns, find the category of title by Google and replace the
values in category values that are the same.
7. Create 6 pivot tables including:
  * SUM of book sales, review amounts and AVERAGE of rating and price for authors
  ![image](https://github.com/user-attachments/assets/a125558b-abe3-4229-9d94-487f7acf680c)
  * SUM of book sales, review amounts and AVERAGE of rating and price for titles
  ![image](https://github.com/user-attachments/assets/2d5e1f79-b96e-4ab3-af02-9a0e8c3dcaaf)
  * SUM of book sales, review amounts and AVERAGE of rating and price for publisher
  ![image](https://github.com/user-attachments/assets/b5cd346f-7915-45aa-a1cc-5228af52a99f)
  * SUM of book sales, review amounts and AVERAGE of rating and price for categories
  ![image](https://github.com/user-attachments/assets/45f5fc54-126c-48fe-90aa-c1e803058b4b)

  * Categories distribution of best-seller books<br/>
  ![image](https://github.com/user-attachments/assets/bebaed40-6e98-44f2-b822-51e350e88852)
  * Authors distribution of best seller authors<br/>
  ![image](https://github.com/user-attachments/assets/3945390a-2f63-4f59-9b6b-80b307474ffa)
### 4. Analysis Summary
Now that we have used spreadsheets to take a quick look as well as making a few pivot table now
we can do our statistical analysis in Python. I am going to import the whole csv file to Kaggle
for analysis:
1. Get a quick description of mean, median and percentile of numeric variables<br/> ![image](https://github.com/user-attachments/assets/ce7031f7-9d8d-4fe5-b252-1edd1a1afd28)

2. Check for incorrect data types and null values<br/> ![image](https://github.com/user-attachments/assets/6ccdb6e4-b28e-4983-abc3-a36aadba21fd)

3. Distribution plot of every variable and boxplot to find outliers<br/> ![image](https://github.com/user-attachments/assets/5ce56832-cc52-4063-a261-1db46fcf2c1d) ![image](https://github.com/user-attachments/assets/1ed96f2f-b308-4040-a23f-2ab4e23dc4f5) ...etc (Read notebook to see more)

4. Get rid of outliers
5. Scatter plot to target variables quantity sales to derive correlation to other variables<br/> ![image](https://github.com/user-attachments/assets/6242373c-9d2d-4efa-8fdc-1c5dc42814be) ...etc

6. Scatter plot of different variables<br/> ![image](https://github.com/user-attachments/assets/a04116f4-d80b-4ddf-9353-9eb0c9b7b650) ...etc

7. Bar chart of categorical variables with numerical to find insights<br/> ![image](https://github.com/user-attachments/assets/e7537c14-5165-4092-bd83-303a186ed507) ...etc

8. Pairplot for regression analysis<br/> ![image](https://github.com/user-attachments/assets/94792186-2251-431e-8e8a-267fc3da2b6d)

9. Implement univariate regression, multivariate regression and gradient boosting to predict quantity sales
10. Evaluate and compare 3 models<br/> ![image](https://github.com/user-attachments/assets/3d967510-d963-4743-898d-dfa06ca31e8b)..etc

### 5. Key findings and Visualization
* The more reviews the book has the more sales it will have
* Books belonging to categories: novel and comedies is the best sellings
* Authors of such books are also very popular
* National Economics University Publisher is the most popular
* Discounts have somewhat correlation to quantity sales
* Most discounts occurs in educational books
* Pages of the book also have somewhat correlation to quantity sales
* Average ratings of books have a mean of 4.6 out of 5.0 so rating is not really a good predictor
* Some recommendation to increase book sales: increase stock for novel and import more types of novel, provide more discounts on novel, decrease stocks for children books, slightly increase stock for self-help and educational books.
Here is the PowerBI dashboard:
![image](https://github.com/user-attachments/assets/8b88d45e-12c4-4648-a828-6d42c832fb03)

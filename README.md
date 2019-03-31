# Price Recommender for Products

In this project, we develop an application that uses machine learning algorithms to recommend selling prices for products. This application can assist manufacturing companies and retailers in pricing the products. The application uses the data about laptops and their features to train the machine learning algorithms. So, given the specifications of a laptop, the application can recommend a good selling price for it. With some modifications, the application can be used for other products than laptops.

## Data Collection
In this project, we crawl [Best Buy's website](https://www.bestbuy.com/) using their [Products API](https://bestbuyapis.github.io/api-documentation/#products-api) and [Categories API](https://bestbuyapis.github.io/api-documentation/#categories-api) to collect data about laptops that can be bought now on Best Buy's website. The following laptop features and specifications are considered in the project: 2-in-1 design, Backlit keyboard, Brand, Color, Number of HDMI ports, Number of USB ports, Battery life, Graphics, Optical drive type, Processor model, Weight, Screen resolution, Screen size, SSD capacity, Total storage, RAM, Touch screen, Average customer review, and price.

## Data Wrangling
Then, we transform our data to the format we need for our analyses. Some examples of data wrangling techniques that we use in this project are as follows. For the columns with very few missing data (i.e. nulls), we drop nulls, since dropping them will not put many data away from our analyses. For the columns with several missing data, we substitute nulls with some estimated values. For example, randomly checking the laptops whose 2-in-1 design value is null suggests us that those laptops are not 2-in-1. So, we substitute the nulls with 0 (i.e. "No" or "Not 2-in-1"). Another data wrangling technique that we use is for extracting numbers from the mix of numbers and texts by removing the text part for example in "Screen Size" column where "x inches" becomes "x". Combining "Battery Cells" and "Battery Life" columns into one cell (i.e. "Battery Life") is another example of data wrangling techniques we use. To do this, we first drop the word "hours" from the "Battery Life" cell and we convert the values to numbers in this column. We keep every row in the "Battery Life" column that has a value. Then, for each missing row in the "Battery Life" column, we substitute the null value with the average battery life for the specific product based on its number of battery cells in the "Battery Cells" column. As another example, some of the columns such as "Processor Model" contain categorical data. We substituted each of these columns with several dummy columns that represent it using 0/1 values.

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mahnazasghari/ProductPriceRecommender/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

# Meet the HF datasets\_old

| Data: the start of it all                       |
| ----------------------------------------------- |
| Sneak peak at datasets                          |
| Getting started with the datasets library       |
| Datasets 🤝 Arrow                               |
| Most common datasets for tasks                  |
| Exploring dataset structures                    |
| Dataset splits and formats                      |
| Data filtering and processing                   |
| Advanced data manipulations                     |
| Batching and iterating                          |
| Loading custom datasets                         |
| Streaming datasets                              |
| Questions to ask before starting with a dataset |



### Sneak peak at datasets



{% hint style="info" %}
<mark style="background-color:purple;">What we will cover:</mark>

* <mark style="background-color:purple;">how to install the library</mark>
* <mark style="background-color:purple;">load datasets, and</mark>
* <mark style="background-color:purple;">perform basic operations such as exploring and filtering data.</mark>
{% endhint %}

***

> #### Problem 1
>
> **I need data. Can to get my data in Hugging Face?**&#x20;
>
> Data is the start of it all: it defines everything you do in your project. Hugging Face is amazing place as has lot of datasets that we can use to jump start building great things AI.



> #### Problem 2
>
> **I found my data, but how can I work with it using Hugging Face tools?**
>
> What you most commonly want to do with the data is to load it, get some information about your data structure and setup, prep your data by doing some common transformation of your data.&#x20;
>
> To summariselo:
>
> data
>
> * load data
> * get info about your data
> * how to prep your data for processing

***





Let's have a closer look at datasets at HF and start working with `datasets` library.

We can find datasets at HF [here](https://www.google.com/url?q=https%3A%2F%2Fhuggingface.co%2Fdatasets) and we can get all the documentation for the library here

We are going to work very close with this library, so bookmark the link!  The library is amazing and simplifies how to access and work with myriads of datasets for an ML/AI project.



Now that you are all setup, the first step is to load a dataset. The easiest way to load a dataset is from the [Hugging Face Hub](https://huggingface.co/datasets). There are already over 900 datasets in over 100 languages on the Hub. Choose from a wide category of datasets to use for NLP tasks like question answering, summarization, machine translation, and language modeling. For a more in-depth look inside a dataset, use the live [Datasets Viewer](https://huggingface.co/datasets/viewer/).

#### 1. Installation

First, ensure you have the `datasets` library installed. If not, you can install it using pip.

`! pip install datasets`

#### Do:

* [ ] Open your Google Collab and use the code above to install the \`datasets\` library.
* [ ] Verify the installation by importing the library with

`import datasets`

#### 2. Loading a Dataset



{% hint style="info" %}
Make sure to check the previous section and setup your API key in GoogleColab to prevent annoying warning
{% endhint %}

We'll start by loading a dataset from the Hugging Face Hub. For this example, let's use the `imdb` dataset. Lets's see where we can find this dataset on the website first!

```
from datasets import load_dataset

# Load the IMDB dataset
dataset = load_dataset('imdb')
```

#### Hands-on Exercise 2

1. In a Python script or Jupyter notebook, load the `imdb` dataset using the code above.
2. Print the loaded dataset to see its structure.

#### 3. Exploring the Dataset (10 minutes)

Once the dataset is loaded, we can explore its contents. This includes viewing the dataset's structure, columns, and a few examples.

```
# View the dataset
print(dataset)

# Access a specific split
train_dataset = dataset['train']

# Check the structure
print(train_dataset.column_names)
print(train_dataset.features)
print(train_dataset[0])
```

#### Hands-on Exercise 3

1. Access the `train` split of the `imdb` dataset.
2. Print the column names and features of the `train` split.
3. Print the first example in the `train` split.

#### 4. Filtering and Selecting Data (10 minutes)

Filtering and selecting data is crucial for preparing datasets for training models. We'll learn how to filter the dataset based on specific conditions.

```
# Filter the dataset to only include positive reviews
positive_reviews = train_dataset.filter(lambda x: x['label'] == 1)

# Select a subset of columns
subset = train_dataset.select(range(1000))
```

#### Hands-on Exercise 4

1. Filter the `train` split of the `imdb` dataset to include only positive reviews.
2. Select the first 1000 entries from the `train` split.
3. Print a few examples from the filtered and selected datasets.

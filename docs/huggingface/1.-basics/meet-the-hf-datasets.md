# Meet the HF datasets

### Sneak peak at datasets



{% hint style="info" %}
<mark style="color:purple;">What we will cover:</mark>

* <mark style="color:purple;">where are datasets at Hugging face</mark>
* <mark style="color:purple;">what is the data workflow</mark>&#x20;
* <mark style="color:purple;">what to use for data workflow with Hugging Face</mark>
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
> What you most commonly want to do with the data is to load it, explore and prep (or transform) your data for further use = put it in the model!&#x20;
>
>

***

To summarise:

<figure><img src="../.gitbook/assets/data_workflow.png" alt="" width="375"><figcaption><p>Data workflow</p></figcaption></figure>

Let's have a closer look at datasets at Hugging Face and see how we can use data workflow with the `datasets` library.

We can find datasets at this special Datasets section at Hugging Face [here](https://www.google.com/url?q=https%3A%2F%2Fhuggingface.co%2Fdatasets) and we also have support for our data workflow in the datasets library . So you see we have both - data repos and tools to work with data.

<figure><img src="../.gitbook/assets/data_tools.png" alt="" width="375"><figcaption><p>Hugging Face repos and library</p></figcaption></figure>

When I am not sure how to do something related to data at Hugging Face, I always go and check docs [here](https://huggingface.co/docs/datasets/index)

I really like this library: it makes working with data simplifies how to access and work with myriads of datasets for an ML/AI project.



### Getting started with the datasets library

Let's start our second Hugging Face project. In&#x20;

{% hint style="info" %}
<mark style="color:purple;">What we will cover:</mark>

* <mark style="color:purple;">install the library</mark>
* <mark style="color:purple;">load datasets, and</mark>
* <mark style="color:purple;">perform basic operations such as exploring and filtering data.</mark>
{% endhint %}

Welcome back!  Let's dig into coding: data and datasets library!

&#x20;In the previous video we started with datasets at Hugging Face, talked about the ML data flow and started our second project. Now - more coding!

We work with one of the most remarkable datasets at Hugging Face: `imdb` dataset [here](https://huggingface.co/datasets/stanfordnlp/imdb) . The IMDB Movie Reviews dataset is sourced from the Internet Movie Database (IMDB) and contains 50,000 highly polarized reviews.

Let's go to the Hugging Face website and have a look at its dataset card.

We can have a quick look at the dataset even without loading it using **Dataset Viewer** and read about the dataset under the [Dataset Summary ](https://huggingface.co/datasets/stanfordnlp/imdb#dataset-card-for-imdb). We see that the dataset includes two columns: text and label.

As you see on the `Splits` view, the dataset is evenly split into 25,000 reviews for training and 25,000 reviews for testing, with each set having an equal number of positive and negative reviews. Each review typically includes:

* **Review Text**: The main body of the review written by the user.
* **Sentiment Label**: A binary label indicating the sentiment of the review (positive or negative).

The size of the dataset is 50,000 reviews, which is manageable and comprehensive for NLP tasks.

But let's go to Google Colab and start coding.













Now that you are all setup, the first step is to load a dataset. The easiest way to load a dataset is from the [Hugging Face Hub](https://huggingface.co/datasets). There are already over 900 datasets in over 100 languages on the Hub. Choose from a wide category of datasets to use for NLP tasks like question answering, summarization, machine translation, and language modeling. For a more in-depth look inside a dataset, use the live [Datasets Viewer](https://huggingface.co/datasets/viewer/).

#### 1. Installation

First, ensure you have the `datasets` library installed. If not, you can install it using pip.

`! pip install datasets`



\# 1. Installing Required Libraries# First, let's install the necessary libraries.!pip install datasets!pip install huggingface\_hub

***

\[ ]#load imdb datasetfrom datasets import load\_datasetdataset=load\_dataset("imdb")# https://huggingface.co/datasets/stanfordnlp/imdbprint(dataset)

***



We are going to work with `imdb` datasets created at Stanford NLP lab.  l love this dataset as it is very simple but at the same time it is big and quite diverse, so we can use it to demonstrate some basic exploration and data prepping.

Let's have a look at the dataset more closely using the Hugging Face website:

We can see some basic information about the dataset in the dataset card.

We also can explore the dataset using Data Viewer on the website and we can see that the dataset has already 3 splits: train, test, and unsupervised split which  is the full dataset with labels removed. But let's start coding:



***

\[ ]# training splittrain\_dataset=dataset\['train']

***

\[ ]test\_dataset=dataset\['test']

***

\[ ]train\_dataset.column\_names

***

\[ ]train\_dataset.features

***

\[ ]train\_dataset\[0]train\_dataset\[-1]

***

\[ ]dataset\[0]

***

\[ ]dataset\['test']\[0]

***

\[ ]positive\_reviews=train\_dataset.filter(lambda x: x\['label']==1)print(positive\_reviews)

***

\[ ]

```
p=train_dataset.filter(lambda x: x['label']==1)
```

***

\[ ]

```
train_dataset.select(range(1000))[1:50]
```

***

arrow\_upwardarrow\_downwardlinkcommenteditdeletemore\_vert\


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

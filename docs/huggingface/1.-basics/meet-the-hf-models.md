# Meet the HF models

| HF Hub                                                                     |
| -------------------------------------------------------------------------- |
| Sneak peak at models: Model Hub                                            |
| Intro to transformer models                                                |
| Tasks and models                                                           |
| Pretrained models: what does it mean                                       |
| Selecting a model                                                          |
| Reading the model card                                                     |
| Trending models guide                                                      |
| Using models for inference                                                 |
| Downloading models                                                         |
| Model outputs and interpretation                                           |
| Customizing model parameters                                               |
| Model widgets                                                              |
| Understanding model limitations                                            |
| Putting this all together: workflow for working with any pretrained models |
| Questions to ask before starting with a model                              |

### HF Hub

Welcome! Let's have a look at Hugging Face hub and think about a small project we can do for our portfolio.

We looked briefly at the Hugging Face website and created an account there. Now, let’s head to Hugging Face hub and a look at all the treasures that are hidden there! And there is a LOT - Hugging Face is one of the best ML platforms that has everything in one place - from data to models and tools to use them on the go.&#x20;

But let's start doing things!

Hugging Face hub is build around three components:

1\. Models! And there are a lot of them there!

2\. Datasets

3\. Documentation - docs

4\. Spaces and community

\
Let's open the HF website - huggingface.co and explore.



![](https://lh7-us.googleusercontent.com/docsz/AD\_4nXesuATu53PmwlYUFtvemIXgpr5YmUrfBAwpOEmwmFQwcGIdxvIg1-PZM49Fcbtn37V8EqmqCr-83N5DGacBBswckLqQbMs5F4tgO0ty8U1r0I\_ZTVTuTQg5Bg0V3BDWe5oqs77huhy1QIktPR\_wMQAhc6Vi?key=pwjwodfWMnUxIFMintqadw)

#### Models

Let's start with models! Hugging Face is the home for thousands of pre-trained models. These models are capable to solve very different tasks from language processing to vision, audio and a multimodal which is a combination of different modalities, such as text and visual in a particular context! But don’t stress we will look at those and play with them!

\


\- \*\*Exploring Models\*\*: On the homepage, click on the “Models” tab. Here, you can filter models by task (e.g., text classification, translation, summarization), libraries (e.g., Transformers, TensorFlow, PyTorch), and more. Each model card provides detailed information about the model, including its usage, performance metrics, and example code snippets.

\


\- \*\*Using Models\*\*: One of the greatest advantages of Hugging Face is the ease of using these models. By copying the provided code snippet, you can integrate a model into your project with just a few lines of code.

\


EXAMPLE

\


&#x20; This simplicity allows both beginners and experienced developers to quickly leverage state-of-the-art models.

\


\### Datasets

\


Next, let's explore the Datasets section. Hugging Face provides access to a multitude of datasets that are crucial for training and evaluating machine learning models.

\


\- \*\*Finding Datasets\*\*: Click on the “Datasets” tab. You can search for datasets based on tasks, languages, and other attributes. Each dataset comes with a detailed card that includes the dataset description, features, and usage examples.

\


\- \*\*Using Datasets\*\*: Hugging Face offers the \`datasets\` library, which allows seamless integration of datasets into your workflow. For instance, to load and use a dataset, you can do:

&#x20; \`\`\`python

&#x20; from datasets import load\_dataset

&#x20; dataset = load\_dataset('imdb')

&#x20; print(dataset\['train']\[0])

&#x20; \`\`\`

&#x20; This library supports various functionalities like dataset manipulation, filtering, and even sharing your own datasets with the community.

\


\### Documentation

\


The documentation provided by Hugging Face is comprehensive and user-friendly. It serves as a valuable resource whether you are just getting started or need advanced guidance.

\


\- \*\*Accessing Docs\*\*: Click on the “Docs” tab. Here, you can find detailed documentation for the various libraries offered by Hugging Face, such as \`transformers\`, \`datasets\`, \`tokenizers\`, and \`accelerate\`.

\


\- \*\*Guides and Tutorials\*\*: The documentation includes step-by-step guides, tutorials, and example notebooks that cover a wide range of topics. Whether you want to fine-tune a model or learn about advanced tokenization techniques, the docs have you covered.

\


\### Spaces and Community

\


One of the most exciting aspects of Hugging Face is its community and collaborative spaces.

\


\- \*\*Spaces\*\*: Spaces is a relatively new feature that allows users to create and share interactive machine learning demos. Powered by Gradio and Streamlit, Spaces enable you to deploy models and datasets in an interactive format that can be accessed and used by others. You can create your own Space to showcase your models or explore Spaces created by others for inspiration.

\


\- \*\*Community Involvement\*\*: The Hugging Face community is vibrant and active. You can join the discussion forums, contribute to projects, and participate in events like sprints and hackathons. The community is a great place to learn, share knowledge, and collaborate with others passionate about AI.

\


\### Getting Hands-On

\


Now that we have an overview, it's time to get hands-on. Here are some practical exercises to get you started:

\


1\. \*\*Experiment with Models\*\*: Choose a model from the Hugging Face Model Hub and integrate it into your project. Try different tasks like text generation, translation, or question answering.

\


2\. \*\*Explore Datasets\*\*: Load a dataset from the Datasets Hub and perform basic data exploration and manipulation. Experiment with filtering and transforming the dataset to suit your needs.

\


3\. \*\*Create a Space\*\*: Use Gradio or Streamlit to create a simple interactive demo of a model. Deploy it on Hugging Face Spaces and share it with the community.

\


4\. \*\*Read the Docs\*\*: Pick a guide or tutorial from the documentation and follow along. Implement the examples and try extending them with your own modifications.

\


Finally!

\


Hugging Face is a treasure trove of AI resources, and by exploring its models, datasets, documentation, and community features, you can significantly boost your machine learning projects. Dive in, experiment, and don't hesitate to reach out to the community for support. Happy exploring!

\
\

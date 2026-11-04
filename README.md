# Open Source GenAI with Ollama

This workshop introduces **Ollama**, an open-source platform for downloading and running generative AI models. We focus primarily on running models locally on a laptop or workstation and explore how different models can be used for chat, document transcription, image analysis, text classification, and document-based question answering.

Local models provide an alternative to cloud-based services such as ChatGPT or Gemini. A model running locally on your laptop or workstation can provide a number of benefits, including:

* Greater control over where and how data is processed
* Offline access to AI models without an internet connection
* No-payment-method experimentation
* Lightweight AI models for portable, offline devices
* Open-source GenAI models

The workshop introduces several types of models available through Ollama and considers how to choose a model for a particular task. We begin by interacting with a general-purpose chat model from the Unix command line, then use Python to work with models for optical character recognition (OCR), image analysis, text classification, structured decision making, and document-based chat. These examples illustrate how generative AI models can be incorporated into larger computational and document-analysis workflows.

Programming experience is not required. Participants can follow the demonstrations and discussion without coding along. Participants with Python or Unix command-line experience are welcome to run or adapt the examples.

> **Note:** Ollama is open-source software, but the models available through Ollama have their own licenses and are not necessarily open source. Local models also have limitations, including hardware and memory requirements, and may not provide the same capabilities as larger cloud-based systems.

## Objectives

By the end of this workshop, participants will be able to:

- Explain some of the benefits and limitations of running generative AI models locally
- Identify situations in which a locally running model might be useful for research or other work
- Describe several types of models available through Ollama, including models for text, images, OCR, audio and transcription, coding, embeddings, and specialized tasks
- Understand how Ollama can be used to download and run models on a local computer
- Compare general-purpose chat models with models designed for specialized tasks
- Describe how Python and command-line tools can be used to interact with locally running models
- Understand how locally running models can be incorporated into document-analysis workflows

## Prerequisites

No previous Python or Unix experience is required to participate in the workshop.

Demonstrations of Ollama in this workshop will use the Unix command line and Jupyter notebooks running Python. Participants with programming or command-line experience may choose to code along, but this is optional.

Participants who want to run the examples on their own computer will need:

- Ollama
- Python
- Jupyter Notebook or JupyterLab
- A Unix command-line environment

## Installing and Running Ollama

Ollama must be installed and running on your computer before using the examples in this workshop.

Installation instructions are available at:

[https://ollama.com/download](https://ollama.com/download)

Once Ollama is installed and running, models can be downloaded from the command line. For example:

```bash
ollama pull gemma3
```

To see models that have already been downloaded:

```bash
ollama list
```

To start an interactive chat with Gemma 3:

```bash
ollama run gemma3
```

The workshop will begin by running a chat-style GenAI model through the command-line interface before moving to Python. The command line provides a simple way to explore Ollama and its models, while Python allows us to incorporate the same models into more sophisticated computational workflows.

Ollama can also be used through graphical chat interfaces, other programming languages, and applications that communicate with the Ollama API.

## Models Used in This Workshop

Ollama provides access to a wide range of models designed for different tasks. Models vary in their capabilities, size, hardware requirements, and licensing.

This workshop uses the following models.

### Gemma 3

[https://ollama.com/library/gemma3](https://ollama.com/library/gemma3)

Gemma 3 is a family of general-purpose models from Google. In this workshop, we use Gemma 3 first as an interactive chat model and later for text classification and document-based question answering.

### DeepSeek-OCR

[https://ollama.com/library/deepseek-ocr](https://ollama.com/library/deepseek-ocr)

DeepSeek-OCR is a vision-language model designed for optical character recognition. We use it to extract machine-readable text from an image of a document.

### Qwen3-VL

[https://ollama.com/library/qwen3-vl](https://ollama.com/library/qwen3-vl)

Qwen3-VL is a vision-language model that can work with both images and text. We use it to describe and interpret the visual content of an advertising image.

### Strands Decider

[https://ollama.com/library/strands-decider](https://ollama.com/library/strands-decider)

Strands Decider is a specialized decision model designed for tasks such as classification, routing, and scoring. Rather than generating a free-form response, a decision model can choose among explicitly defined options and return a structured result.

Ollama provides additional background on Jev-style decision models here:

[Ollama now supports Jev-style decision models](https://registry.ollama.com/blog/ollama-now-supports-jev-style-decision-models)

## Data

The workshop uses documents from the **UCSF Industry Documents Library**, a digital archive of documents created by industries that influence public health.

[https://www.industrydocuments.ucsf.edu/](https://www.industrydocuments.ucsf.edu/)

The examples include several forms of document data:

- [An image of an article](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/media/pmcj0045.png) used to demonstrate OCR
- [The text extracted from that article](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/media/pmcj0045.txt) used for text classification and document chat
- [An advertising image](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/media/glnj0229.png) used to demonstrate visual analysis

Using related materials across several examples makes it possible to compare how different kinds of models work with textual and visual information.

## Workbooks

### [Extract-Text.ipynb](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/Extract-Text.ipynb)

This workbook uses **DeepSeek-OCR** to extract text from an image of a document from the UCSF Industry Documents Library.

The example demonstrates how a locally running vision-language model can be used for OCR and how the resulting text can be saved for subsequent analysis.

### [Describe-Image.ipynb](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/Describe-Image.ipynb)

This workbook uses **Qwen3-VL** to describe and interpret an advertising image from the Industry Documents Library.

Rather than simply extracting text, this example asks a vision-language model to describe and interpret visual information contained in the image.

### [Classify-Text-Chat.ipynb](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/Classify-Text-Chat.ipynb)

This workbook uses **Gemma 3**, a general-purpose chat model, to classify text into a set of categories.

The example illustrates how instructions provided through a conventional chat prompt can be used to turn a general-purpose generative model into a simple text classifier.

### [Classify-Text-Decision.ipynb](https://github.com/UCSF-DSOS/Local-AI-With-Ollama/blob/main/Classify-Text-Decision.ipynb)

This workbook uses **Strands Decider** to perform text classification using a Jev-style decision model.

Instead of asking a general-purpose chat model to generate a free-form answer, the example defines possible choices and criteria and asks the model to make a structured decision.

Together, `Classify-Text-Chat.ipynb` and `Classify-Text-Decision.ipynb` provide an opportunity to compare classification using a general-purpose chat model with classification using a model designed specifically for structured decisions.

### Document-Chat.ipynb

This workbook uses **Gemma 3** to interact with text previously extracted from a document.

The extracted document text is supplied to the model as context, allowing the user to ask questions about the document and continue with follow-up questions.

This final example returns to the general-purpose model introduced at the beginning of the workshop and demonstrates how Python can turn a locally running chat model into a simple document-analysis application.

## Relationship to the Workshop Series

This workshop is part of a broader UCSF Library curriculum on computational data and document analysis with Python, SQL, machine learning, and AI.

The workshop series emphasizes applied practice, using programming and computational tools to work with real-world data and document collections. Generative AI is introduced alongside more traditional programming, natural language processing, machine learning, and data-management approaches.

Ollama provides a useful environment for exploring generative AI without requiring participants to create a paid commercial AI account or enable billing for a cloud-based API. Running models locally also provides opportunities to consider questions around local computation, data privacy, reproducibility, model selection, and the role of AI within larger computational workflows.

## Instructor

Geoffrey Boushey is a computational and research data science specialist at UCSF and a member of the Library's Data Science and Open Scholarship team. Geoff teaches courses and provides consultations on foundational programming, data analysis, and AI techniques including Python, SQL, Unix, and Version Control.

## Additional Resources

- [Ollama](https://ollama.com/)
- [Ollama Model Library](https://ollama.com/search)
- [Ollama Documentation](https://docs.ollama.com/)
- [UCSF Industry Documents Library](https://www.industrydocuments.ucsf.edu/)
- [AI for Research — UCSF Library](https://guides.ucsf.edu/AIforResearch)

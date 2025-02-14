# LLM interface between user, data and optimization model for demand side flexibility

## Table of contents
* Description
* Project structure
* Instalation
* Documentation
* Usage
    * data
    * model
    * optimization
    * Pieces of advice

## Description

This project defines a convex optimization problem that models a house electricity consumption and a LLM (Large Language Model) pipeline that extract the wanted data from different sources with the RAG method (Retrieval Augmented Generation).

## Project structure

TODO add folder tree and file description

* build
    * ADD TODO
* doc
    * folder containing the documentation
* img
    * default folder where the figures are saved
* data
    * default folder where the data are saved
* rag
    * rag.py
        * script that defines the LLM pipeline functions
    * user.py
        * script that defines the optimization problem
    * model.py
        * script that defines the **model** command
    * data.py
        * script that defines the **data** command
    * optim.py
        * script that defines the **optim** command
* test
    * test.py
        * script that test all the scripts from rag directory
* LICENSE.txt
* README.md
* setup.py
    * ADD TODO
* setup.cfg
    * ADD TODO
* requirements.txt
    * list all required libraries

## Instalation

Several installation are possible. We will describe a simple one.

- After having downloaded the project and having extracted it, go to your terminal and move your working directory to the newly downloaded folder **RAG**.

- Create a python environment with the requirements listed in requirements.txt file:
``` bash
conda create --name <env> --file requirements.txt
```

- Activate this environment and type the following command :
``` bash
pip install .
```

- To check your installation you can try the following commands:
``` bash
cd test
python test.py 1
python test.py 2
```
If everything is fine, the tests should all pass.

## Documentation 

TODO
The documentation is generated by the sphinx library. Here is a list of the command to access the html version :

``` bash
cd doc
make html
python -m http.server
```

The documentation will then be available on the following link : http://localhost:8000/build/html/index.html.

The html file are also accessible here ./doc/build/html.

## Usage

TODO
The rag library allows the instalation of three terminal commands :

- data
- model
- optim

We will now develop how to use those functions.

### data
TODO
GOAL : Create a FAISS object given a document. This document is going to be embedded and divided into several chuncks.

Specifications :

* Mandatory
    * ADD

* Not mandatory
    * ADD

Examples :

``` bash
data TODO 
```

TODO ADD OUTPUT 

``` bash
data TODO 
```

TODO ADD OUTPUT 

### model
TODO
GOAL : Create a FAISS object given a document. This document is going to be embedded and divided into several chuncks.

Specifications :

* Mandatory
    * ADD

* Not mandatory
    * ADD

Examples :

``` bash
data TODO 
```

TODO ADD OUTPUT 

``` bash
data TODO 
```

TODO ADD OUTPUT 

### optim
TODO
GOAL : Create a FAISS object given a document. This document is going to be embedded and divided into several chuncks.

Specifications :

* Mandatory
    * ADD

* Not mandatory
    * ADD

Examples :

``` bash
data TODO 
```

TODO ADD OUTPUT 

``` bash
data TODO 
```

TODO ADD OUTPUT 

### Pieces of advice

TODO add

## TODO list

* make the data loading part able to receive args like url or filepath and to deal with it
* make data function it more adaptative
* define a custom dataloader that will adapt to different data type for easier code
* make a structured project architecture 
    * able to call function from terminal (ex: data --url https://... --type csv and llm --faiss faiss1 faiss2 --query Myqueries.txt) 
    * and with a visual interface like gradio
* make a documentation, so improve function description  (see : https://opensource.com/article/19/11/document-python-sphinx, https://google.github.io/styleguide/pyguide.html#381-docstrings)
* clean README
* try to see python guide for a prettier code (PEP8 https://www.python.org/dev/peps/pep-0008/)
* display advancement (tqmd)
* adapt code to gpu or make optional
* allow different model and embeddings
* define tests for all functions and make them as robust as possible (raise errors if not possible)
* use function with llm to format output, see : https://www.promptingguide.ai/applications/function_calling
* test all improvements possibilities, see list below :
    ### Improvements
    
    Measuring performance:
    
    this means building a small evaluation dataset, then monitor the performance of your RAG system on this evaluation dataset.
    
    Tune the chunking method:
    * Size of the chunks
    * Method: split on different separators,use semantic chunking…
    * Change the embedding model
    
    Other
    * Try another chunking method, like semantic chunking
    * Change the index used (here, FAISS)
    * Query expansion: reformulate the user query in slightly different ways to retrieve more documents.
    
    Reader
    * Tune the prompt
    * Switch reranking on/off
    * Choose a more powerful reader model
    
    See:
    * https://huggingface.co/learn/cookbook/rag_evaluation
    * https://huggingface.co/learn/cookbook/semantic_cache_chroma_vector_database
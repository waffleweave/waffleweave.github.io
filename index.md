# Abstract
LOOM is a programming tool that simplifies the developer's workflow. It gives quick and easy access to documentation and real code related to the developer's current task without leaving their development environment. We use IBM Watson tools and services to provide context-based suggestions from curated resources.  This proof-of-concept shows great promise for speeding up development for both experienced and inexperienced software engineers.

# Summary

LOOM is an extension for Visual Studio Code (VS Code). IBM Watson services process natural language and code queries to collections of relevant documents. The user can search keywords or questions like with a traditional search engine or search using their code as the query. The code queries are sent through IBM Watson Natural Language Classifier, which categorizes your code into the nearest category we have references on. The collection contains both common algorithms and python standard library reference material. This material has descriptions and working python sample code.

This is a proof of concept; python is a simple language with little clutter, which makes NLC work better and sample code simpler. This could be extended to other languages and/or more categories and documents for reference material.

# Design Decisions

## Visual Studio Code Extension

Early in the design process the LOOM team had to consider for what platform we would develop this tool.  Early options considered included: Eclipse IDE, VS Code, and a custom text editor we would build.  Ultimately, VS Code was selected for its apparent ease of development and flexibility.

## Python Language Support

Another early design choice was selecting a language to support.  While the collection of results would need to be curated/created regardless of language, there were concerns about integration with IBM Watson tools and language parsing.  In the end Python was chosen over languages like C, C++, and Java for its syntactic simplicity and minimal boilerplate code.

## Natural Language Classifier

Searching for information without knowing its name is hard with a search engine. Being able to just use your code as the search term makes LOOM even faster and easier. To process the code and understand what you are searching for we used IBM Watson NLC. It was more natural for our problem than their Conversation service. It could take code samples and naturally create a search term for our Discovery service. 

## Algorithm Support

We currently support a number of basic algorithms, as well as some of the basic python documentation. These were chosen because they are simple but easily forgotten or confused things that will effectively demonstrate how LOOM can help your workflow. Other syntax features are already present in modern IDEs.

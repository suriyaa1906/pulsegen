# pulsegen
A Python-based tool that crawls product documentation websites and extracts modules, submodules, and their descriptions into a structured JSON format.
Assignment 3 – Pulse: Module Extraction AI Agent
Overview

This assignment focuses on building a small AI-based tool that can understand and organise information from product help or documentation websites.

The goal is to automatically identify main modules, their submodules, and provide clear descriptions for each of them by analysing the structure and content of the documentation pages.

The solution works only with the content available on the given URLs and does not rely on any external knowledge.

Problem Statement

Modern products have large documentation websites that are difficult to analyse manually.
This assignment aims to simplify that process by creating an agent that:

Crawls documentation websites

Understands how content is structured

Groups related information logically

Outputs the results in a structured JSON format

Approach

The solution follows a simple and practical approach:

The documentation URL is taken as input

The website is crawled recursively, limited to internal links

Relevant content such as headings, paragraphs, and lists is extracted

Heading hierarchy is used to identify:

Modules (main sections)

Submodules (subsections)

Descriptions are generated using only the extracted text

The final output is saved as a JSON file

This approach keeps the logic transparent and easy to understand.

Features

Recursive crawling of documentation pages

Removal of navigation and irrelevant content

Automatic detection of modules and submodules

Clean and readable JSON output

Works on multiple documentation websites

Can be executed easily in Google Colab

Technology Used

Language: Python

Libraries:

requests

beautifulsoup4

lxml

Environment: Google Colab / Local Python setup

Input

One or more documentation URLs, for example:

https://help.instagram.com
https://wordpress.org/documentation/

Output

The output is generated as output.json in the following structure:

[
  {
    "module": "Account Settings",
    "Description": "Contains options related to managing account preferences and privacy.",
    "Submodules": {
      "Change Username": "Explains how users can update their username.",
      "Deactivate Account": "Provides steps to temporarily disable the account."
    }
  }
]

How to Run (Google Colab)

Install required libraries:

!pip install requests beautifulsoup4 lxml


Paste the assignment code into a Colab cell and run it.

Download the generated output:

from google.colab import files
files.download("output.json")

Testing

The program was tested using different real documentation websites such as:

Instagram Help Center

WordPress Documentation

Zluri Help Center

Chargebee Documentation

This helped verify that the logic works across different documentation structures.

Assumptions

Documentation pages follow a basic heading structure

Important information is available in text-based HTML elements

Only internal links are relevant for crawling

Limitations

JavaScript-heavy websites may not be fully supported

Very deeply nested documentation may reduce accuracy

Crawl depth is intentionally limited to avoid performance issues

Future Improvements

Use semantic similarity for better grouping

Add confidence scores for modules

Support JavaScript-rendered pages

Expose the functionality as an API

Author

Suriyaa M
Final Year B.E. CSE (AI & ML)

Assignment Chosen

Assignment 3 – Pulse: Module Extraction AI Agent

# BDD in Python Behave

## Overview

The project presents behaviour-driven development (BDD) tests in Python, written
using [Behave](https://behave.readthedocs.io/en/stable/index.html). 

Other technologies used: [Selenium WebDriver](https://www.selenium.dev/documentation/webdriver/), [WebDriver Manager](https://github.com/SergeyPirogov/webdriver_manager).

Tested app is a demo store [SwagLabs](https://www.saucedemo.com/).

## Requirements
* Python 3.10 or higher
* Optional: Git, PyCharm or VSCode with an extension that supports BDD

## User stories and test scenarios

Exemplary user stories cover the main functionalities of the app. Based on them, test scenarios were written 
in the [Gherkin language](https://behave.readthedocs.io/en/stable/philosophy.html#the-gherkin-language):

- Scenario: (explain scenario).
    - Given (how things begin),
    - when (action taken),
    - then (outcome of taking action).

Scenarios can be found in the feature files as per the table:

| Title             | User story                                                                                            | Test scenarios            | Step definition        |
|-------------------|-------------------------------------------------------------------------------------------------------|---------------------------|------------------------|
| Log into the app  | As a user, <br />I want to be able to log in with registered data <br />so that I can access the app. | feature/login.feature     | feature/steps/login.py |                                                                                                              |                      |                                                   |
| Sort inventory    | As a user, <br />I want to be able to sort items by their names and prices.                           | feature/inventory.feature | feature/steps/store.py |                                                                                                                     |                      |                                                   |
| Manage a cart     | As a user, <br />I want to view the shopping cart, add and remove items.                              | feature/cart.feature      | feature/steps/store.py |
| Checkout an order | As a user, <br />I want to checkout my order<br /> so that I can complete shopping.                   | feature/checkout.feature  | feature/steps/store.py |

## Project structure

Feature files are arranged by a business functionality (e.g. `cart.feature` contains all tests related to a cart) while step definitions by a domain, because they are shared by different tests (e.g. `store.py` contains actions that a user can take when logged in the store).

`features_list.txt` defines the scope and sequence of the tests.

The feature directory has the following structure:

```
features/
features/login.feature
features/inventory.feature
features/cart.feature
features/checkout.feature
features/environment.py
features/features_list.txt
features/steps/
features/steps/login.py
features/steps/store.py
```

## Setup

Clone this repository:

```bash
git clone <repo-url>
```

```bash
cd behave-bdd-swaglabs
```

Activate a virtual environment:

```bash
python -m venv venv
```

```bash
venv\Scripts\activate.bat
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run all tests:

```bash
behave
```

Or run tests in a given order and scope:

```bash
behave @features\features_list.txt
```

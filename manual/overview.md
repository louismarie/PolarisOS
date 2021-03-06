# General Overview of the Project

The project is divided into three directories:

- `app` regrouping the backend of the solution.
- `front` regrouping the frontend of the solution.
- `tests` regrouping the tests of the solution.

## Backend

The directory is subdivised into:

- `app.js`: the main entry point of the application.
- `mappings`: the ElasticSearch mappings of the solution.
- `settings`: the ElasticSearch settings for each mapping.
- `config`: the general config of the solution (production, development, test).
- `initializations`: all the API routes needed by the backend to work.
- `logger.js`: the logger of the solution (based on Winston).
- `modules`: the main logic of the backend.

### Modules

The modules directory is sudivised into:

- `auth`: responsible for checking the authentication of a user (will s/he be a 'real' one or an API key).
- `exceptions`: collection of all the exceptions that the program can throw.
- `rate_limit`: a small and easy-to-use rate limiter to avoid getting DDoS when using the APIs.
- `utils`: a set of utils.
- `entities`: all the data models required by the program (see Data model for more details).
- `pipeline`: the standardized pipeline of the program (see Pipeline for more details).

## Frontend

The frontend of the solution is subdivised into:

- `common`: the common utils, components shared by the front-office & the back-office.
- `backoffice`: the pages / components of the back-office.
- `frontoffice`: the pages / components of the front-office.

### Common

Common has multiple directories:

- `api`: everything related to backend discussion: routes used to call the backend, fetching functions, and messages used for mutations in Vuex.
- `components`: every reusable Vue.js components used throughout the application.
- `mixins` : every Vue.js mixins used throughout the application.
- `store`: the Vuex's store.
- `style`: CSS templates of the application (back-office & front-office).
- `utils`:  couples of utility functions to help you build things faster.

### Front-office & Back-office folders

- `components`: every reusable Vue.js components only used for the front-office/back-office (it is the case for the header, navbar, footer of the application).
- `fonts`: custom fonts that are copied to the public folder to be served and used (for custom website based on customers' graphic recommendations).
- `imgs`: pictures, logos, ... used in the front-office/back-office.
- `pages`: pages used in the front-office (deposit, publication view, and so on).

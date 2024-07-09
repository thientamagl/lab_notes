# MYCO PORTAL NOTES

## Purposes

Fundamentally revamp the UI of the web system "Local Government My Page."

# Design strategy

[Atomic Design](https://atomicdesign.bradfrost.com/chapter-2/)

Summary

- Atoms:
  - Define the smallest building blocks of the UI that can't be broken down any further
  - Such as buttons, input fields, labels, and icons.
- Molecules:
  - Combine atoms to form more complex UI components
  - Such as a search bar (input field + button) or a form group (label + input field).
- Organisms:
  - Assemble molecules and atoms to create more substantial, reusable sections of the interface
  - Such as navigation bar, footer, or card component.
- Templates:
  - Create page-level designs by arranging organisms into a cohesive layout, ensuring consistency and reusability across different pages.
  - Such as layout of home page in many curcumstances: loading -> show skeleton, no data -> no data field, error -> error field,...
- Pages:
  - Implement specific instances of templates, populating them with real content to reflect actual use cases and verify the design’s flexibility and completeness.

## Technical stacks

### UI Development

| Package                         |   Version    | Purpose                                                                        |        Note        |
| :------------------------------ | :----------: | :----------------------------------------------------------------------------- | :----------------: |
| Next.js (next)                  |    13.3.1    | framework (run `npx next --verion` for checking version)                       |                    |
| react                           |    18.2.0    | core library                                                                   |                    |
| @types/react                    |   17.0.15    | type definition of React, enable TypeScript support                            |                    |
| react-dom                       |    18.2.0    | core library                                                                   |                    |
| aspida                          |    1.0.2     | generates type-safe API clients from OpenAPI or other API specifications       |                    |
| @aspida/axios                   |    1.10.2    | integrate axios with aspida                                                    |                    |
| axios                           |    0.21.1    | make HTTP request                                                              |                    |
| body-scroll-lock                | 4.0.0-beta.0 | enable body scrool locking                                                     |       no use       |
| dompurify                       |    2.4.1     | clean up potentially dangerous HTML content before injecting to web app        |       no use       |
| @types/dompurify                |    2.4.0     | type definition for dompurify                                                  |       no use       |
| express                         |    4.18.1    | building web server and design APIs                                            |       no use       |
| micromodal                      |    0.4.10    | create modal                                                                   | use in /public (?) |
| noramlize.css                   |    8.0.1     | cross-browser consistency in the default styling                               |                    |
| platform                        |    1.3.6     | platform (browser, os, device) detection                                       |                    |
| @types/platform                 |    1.3.4     | type definition for platform                                                   |                    |
| postcss                         |    8.3.6     | transforming styles with JS plugins                                            |                    |
| postcss-custom-media            |    8.0.0     | manage media queries more efficiently                                          |                    |
| postcss-flexbugs-fixes          |    5.0.2     | ensures flexbox layouts work consistently across browsers                      |       no use       |
| postcss-loader                  |    6.1.1     | intergrating PostCSS with webpack                                              |       no use       |
| postcss-preset-env              |    6.7.0     | use modern CSS features and ensures compatibility with older browsers.         |                    |
| prettier                        |    2.3.2     | code formatter                                                                 |                    |
| react-content-loader            |    6.2.0     | create placeholder loading                                                     |                    |
| react-datepicker                |    4.8.0     | date picker component                                                          |                    |
| react-hook-form                 |    7.30.0    | manage form                                                                    |                    |
| react-html-parser               |    2.0.2     | convert HTML strings into React component                                      |                    |
| react-infinite-scroll-component |    6.1.0     | make infinite scroll                                                           |                    |
| react-modal                     |    3.14.4    | modal component                                                                |                    |
| @types/react-modal              |    3.13.1    | typescript definition for react-component                                      |                    |
| react-scroll                    |    1.8.6     | react component for animating vertical scrolling                               |                    |
| @types/react-scroll             |    1.8.4     | type definition for react-scroll                                               |                    |
| react-select                    |    4.3.1     | select component                                                               |                    |
| react-string-replace            |    1.1.1     | replace parts of a string with React Component/HTML (highlight, custom format) |                    |
| react-toastify                  |    9.0.1     | create toast message                                                           |                    |
| sass                            |    1.37.0    | styling                                                                        |                    |
| sweetalert2                     |    11.4.8    | create alert component                                                         |                    |
| sweetalert2-react-content       |    5.0.6     | enhancer adding support for React elements as content                          |       no use       |
| typescript                      |    5.0.4     | add type to JavaScript                                                         |                    |
| zxcvbn                          |    4.4.2     | password strength estimator                                                    |                    |
| @types/zxcvbn                   |    4.4.4     | type definition for zxcvb                                                      |                    |
| @chatscope/chat-ui-kit-react    |    1.8.3     | build chat UI                                                                  |                    |
| @chatscope/chat-ui-kit-styles   |    1.2.3     | style chat UI                                                                  |                    |
| @emotion/react                  |    11.9.3    | creating styled components (applying styles and managing themes)               |       no use       |
| @emotion/styled                 |    11.9.3    | style React component using styled-component-like API                          |       no use       |
| @line/liff                      |    2.22.2    | integrate LINE functionality into web app                                      |                    |
| @mui/material                   |    5.9.2     | react component library                                                        |                    |
| @ramonak/react-progress-bar     |    5.0.3     | progress bar component                                                         |                    |
| @splidejs/react-splide          |    0.7.12    | slider/carousel component                                                      |                    |
| @types/react-infinite-scroller  |    1.2.3     | type definition for react-infinite-scroller                                    |                    |
| @types/node                     |   17.0.38    | type definition for Node.js, enable TypeScript support                         |                    |

### Linter

| Package                               | Version | Purpose                                                            |  Note  |
| :------------------------------------ | :-----: | :----------------------------------------------------------------- | :----: |
| eslint                                | 8.48.0  | pattern checker for JavaScript                                     |        |
| eslint-plugin-rulesdir                |  0.0.2  | custom ESLint rules by specifying them in a local directory        |        |
| eslint-config-next                    | 13.3.1  | ESLint rules for Next project                                      | no use |
| eslint-plugin-react                   | 7.33.2  | ESLint plugin for linting React app                                | no use |
| eslint-plugin-unused-imports          |  2.0.0  | ESLint plugin designed to identify and remove unused imports       |        |
| @typescript-eslint/eslint-plugin      | 5.36.1  | ESLint rules tailored to TypeScript’s syntax and best practices    |        |
| @typescript-eslint/parser             | 2.36.1  | allows ESLint to understand TypeScript syntax and type information |        |
| @typescript-eslint/experimental-utils | 5.62.0  | assist in creating and managing custom ESLint rules                | no use |

### Code format

| Package  | Version | Purpose        | Note |
| :------- | :-----: | :------------- | :--: |
| prettier |  2.3.2  | code formatter |      |

### Testing

| Package                      | Version | Purpose                                                              | Note |
| :--------------------------- | :-----: | :------------------------------------------------------------------- | :--: |
| jest                         |   28    | test library for unit test, integration test, snapshot test          |      |
| jest-environment-jsdom       |   28    | provides a JSDOM environment for running tests                       |      |
| @testing-library/jest-dom    | 5.16.5  | provides custom matchers for Jest to improve testing of DOM elements |      |
| @testing-library/react       | 13.4.0  | testing library for React applications(focus on user's perspective)  |      |
| @testing-library/react-hooks |  8.0.1  | testing library for React Hooks                                      |      |
| @types/jest                  | 29.0.0  | type definition for jest                                             |      |

### Other

| Package                             | Version | Purpose                                                     | Note |
| :---------------------------------- | :-----: | :---------------------------------------------------------- | :--: |
| @openapitools/openapi-generator-cli |  2.6.0  | command-line interface (CLI) tool for the OpenAPI Generator |      |

## Project Structure

```
src
  ├───assets
  |                         // Styling file (*.scss) and config
  ├───components            // Components definition
  │ ├───atoms
  │ ├───organisms
  │ └───templates
  |
  ├───constants             // Constant Classess
  |
  ├───featureHooks
  │
  ├───injectorHooks
  │
  ├───libs                   // Config libraries
  │
  ├───models
  |
  ├───pages
  │
  └───types                 // types definition
```

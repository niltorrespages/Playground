# Security tools for Software Deployment
<sup>last update October 2023</sup>

There are multiple security tools and scans that we can use to test different elements of the security pipeline to 
ensure a robust application.


## SCA - Software Composition Analysis

SCA tools scan the code for dependencies and check if they have any vulnerabilities. With different tools come different
capabilities. It's important to know how the tool works and what technologies it can analyze. For a microservice oriented
architecture it can be useful to scan the whole image if the tool is capable of detecting both the vulnerabilities in 
the os and the libraries used by the application.

Typical **Open Source** tools can scan only one technology. The following are a few examples:

- Javascript: Retire.js or npm@6
- Python: Safety
- Ruby: Bundler
- PHP: Composer
- Java: OWASP Dependency Scanner

For a more professional scan we can have tools like Snyk that can provide us a full scan of all major technologies

## SAST - Static Application Security Testing

:material-progress-wrench:

## DAST - Dynamic Application Security Testing

:material-progress-wrench:

## IAST - Interactive Application Security Testing

:material-progress-wrench:

## Binary Authoritzation

:material-progress-wrench:

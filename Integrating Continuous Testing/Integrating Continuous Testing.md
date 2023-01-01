# Integrating Continuous Testing

# Understanding Test Types

## Functional Tests

Functional tests are used to test whether the desired functionality is actually realized by the application.

## Non-Functional Tests

Non-functional tests are used to verify whether the other desired properties of an application are realized and that undesirable properties are not present.

## Understanding Test Types

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d050607f-22b1-466d-9762-248ebf4b6e07/Untitled.png)

# Flaky tests

Flaky tests are tests that fail with no evident change in code or configuration, or the code works on a local machine but fails with continuous integration. Upon retrying the test execution multiple times, the test eventually passes.

# Tips

- Make sure you  have more idea about Functional and nonfunctional testing
- How to use functional and nonfunctional testing in pipelines
- How to enable flaky tests which are causing the build randomly.
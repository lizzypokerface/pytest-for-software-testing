# pytest-for-software-testing

PyTest Proficiency: Best Practices for Crafting Effective Tests

## What is PyTest?

- **Testing Framework for Python**
  PyTest is a widely-used testing framework for Python. It is designed to make testing simple and scalable by offering a
  rich set of functionalities that help developers write robust test cases with minimal effort.

- **Auto-discovery of Tests**
  PyTest can automatically discover test files and test functions based on their naming conventions (e.g., PyTest
  requires that your files be prefixed with `test_`, and all test classes should start with `Test`). This means you
  don't need to explicitly register your tests or maintain a test registry. It simplifies test execution by allowing you
  to run all tests in your project with a single command.

- **Rich Assertion Introspection**
  When a test fails in PyTest, it provides a detailed and clear breakdown of why it failed. This includes the values
  involved and where the assertion failed, making it easy for developers to understand what went wrong and how to fix
  it. This rich introspection speeds up debugging and improves the efficiency of the testing process.

- **Supports Parameterized and Fixture-based Testing**
  PyTest allows you to run a single test function multiple times with different arguments using parameterized tests.
  This helps achieve broad test coverage with minimal code. Additionally, the fixture system enables you to set up and
  tear down test environments efficiently, making your tests more readable and maintainable.

## Why PyTest?

- **Simplified Syntax**
  PyTest allows you to write test cases using plain `assert` statements, making the syntax simple and intuitive. This
  reduces the learning curve for new developers and helps maintain clean, readable test code.

- **Rich Assertion Introspection**
  As mentioned, PyTest's detailed failure reports help developers quickly identify and resolve issues. This feature
  ensures that even complex test failures are easy to diagnose, enhancing the overall testing efficiency.

- **Powerful Fixture System**
  PyTest's fixture system is both flexible and powerful, allowing for complex setup and teardown operations. Fixtures
  can be scoped (e.g., per test, per module, per session) and have auto-reuse settings. This helps manage dependencies
  and shared states across tests efficiently, leading to more organized and reusable test code.

- **Compatibility**
  PyTest can run tests written for other testing libraries like `unittest` or `nose`. This makes it easy to migrate
  existing tests to PyTest without significant rework. The concepts and functionality of PyTest are transferable, which
  means developers familiar with other testing libraries can quickly adapt to PyTest.

- **Extensibility**
  PyTest has a rich plugin architecture, allowing you to extend its capabilities with third-party plugins. There are
  many plugins available, such as `pytest-django` for testing Django applications. This extensibility ensures that
  PyTest can be tailored to meet the specific needs of your project, enhancing its functionality and adaptability.

## PyTest Concepts

- **Class-Based Tests**
    - Utilize classes to group related tests, promoting code organization and reusability.

- **Fixtures**
    - Implement reusable setup and teardown code for tests, enhancing efficiency and maintainability.

- **Mark and Parameterize**
    - Use markers to categorize tests and `parametrize` to run a test with multiple sets of data, increasing test
      coverage with minimal code duplication.

- **Mocking**
    - Simulate dependencies and isolate units of code for testing, ensuring tests remain independent and focused.
    - Use mocking when tests depend on external programs that cannot guarantee the same result each time (e.g., database
      queries or API calls that may yield different outcomes).
    - For a list of other techniques used in software testing, see the appendix.

## Up and Running

This project requires Python 3.10 or higher.

### Setup

Create a [virtual environment](https://docs.python.org/3/library/venv.html) in the root directory:

```sh
python3 -m venv env
source env/bin/activate
```

Install [Poetry](https://python-poetry.org/docs/cli/) for dependency management:

```sh
env/bin/pip install -U pip setuptools
env/bin/pip install poetry  
```

Install project dependencies:

```sh
poetry install
```

### Running Tests

**Running All Tests**

Execute all tests with the following command (add `-v` for verbose output):

```sh
poetry run pytest
```

## Reference material

* [Full pytest documentation](https://docs.pytest.org/en/7.4.x/contents.html)
* [unittest.mock](https://docs.python.org/3/library/unittest.mock.html)

## Appendix

### Other techniques used in software testing

1. **Mocking**
    - **Description**: Creating mock objects that mimic the behavior of real objects in controlled ways. Used to isolate
      and test specific pieces of code.

2. **Stubbing**
    - **Description**: Providing pre-defined responses to method calls. Stubs do not simulate the full behavior of real
      objects but return specific results needed for the test.

3. **Faking**
    - **Description**: Implementing simpler versions of real objects that work like the real ones but are simpler and
      faster. Fakes often have the same API but with a limited set of functionalities.

4. **Spying**
    - **Description**: Similar to mocks, but in addition to mimicking the behavior, spies also record information about
      how they were used (e.g., which methods were called and with what arguments).

5. **Shims**
    - **Description**: A shim is a piece of code that intercepts calls and can modify behavior. Shims can be used to
      adapt code without modifying the original source.

6. **Sandboxes**
    - **Description**: Creating a controlled environment where tests can run isolated from the real environment. This is
      useful for testing code that interacts with external systems.

7. **Service Virtualization**
    - **Description**: Simulating the behavior of dependent systems that are not readily available or are difficult to
      access during testing. Service virtualization can mimic APIs, databases, or other services.

8. **Dependency Injection**
    - **Description**: A design pattern where an object receives its dependencies from an external source rather than
      creating them itself. This allows for easy replacement of dependencies with mocks or stubs during testing.

9. **Test Doubles**
    - **Description**: General term for any kind of pretend object used in place of a real object for testing purposes.
      This includes mocks, stubs, fakes, and spies.

10. **Emulators**
    - **Description**: Software that replicates the behavior of a specific environment or hardware. Emulators are often
      used in testing applications meant to run on different platforms or devices.

11. **Simulators**
    - **Description**: Similar to emulators, but simulators recreate only the essential aspects of an environment or
      system, often at a higher level. Simulators are used when detailed replication is not necessary.

12. **In-Memory Testing**
    - **Description**: Testing using in-memory databases or other in-memory data structures to avoid the overhead of
      real database operations. This technique is often used to speed up tests and make them more predictable.

Each of these techniques helps isolate and test specific parts of a system, making it easier to write reliable and
maintainable tests. The choice of technique often depends on the particular requirements and constraints of the project
being tested.
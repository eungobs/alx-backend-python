# Project Title

Brief description of the project.

## Resources

Read or watch:

- [unittest](https://docs.python.org/3/library/unittest.html) — Unit testing framework
- [unittest.mock](https://docs.python.org/3/library/unittest.mock.html) — mock object library
- [How to mock a readonly property with mock?](https://stackoverflow.com/questions/16782112/how-to-mock-a-readonly-property-with-mock)
- [parameterized](https://pypi.org/project/parameterized/)
- Memoization

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- The difference between unit and integration tests.
- Common testing patterns such as mocking, parametrizations, and fixtures.

## Requirements

- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- The first line of all your files should be exactly `#!/usr/bin/env python3`
- A `README.md` file, at the root of the folder of the project, is mandatory
- Your code should use the pycodestyle style (version 2.5)
- All your files must be executable
- All your modules should have documentation (e.g., `python3 -c 'print(__import__("my_module").__doc__)'`)
- All your classes should have documentation (e.g., `python3 -c 'print(__import__("my_module").MyClass.__doc__)'`)
- All your functions (inside and outside a class) should have documentation (e.g., `python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`)
- A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class, or method (the length of it will be verified)
- All your functions and coroutines must be type-annotated.

## Required Files

- utils.py (or download)
- client.py (or download)
- fixtures.py (or download)

## Tasks

### 0. Parameterize a unit test

Familiarize yourself with the `utils.access_nested_map` function and understand its purpose. Play with it in the Python console to make sure you understand.

In this task, you will write the first unit test for `utils.access_nested_map`.

Create a `TestAccessNestedMap` class that inherits from `unittest.TestCase`.

Implement the `TestAccessNestedMap.test_access_nested_map` method to test that the method returns what it is supposed to.

Decorate the method with `@parameterized.expand` to test the function for the given inputs.

```python
nested_map={"a": 1}, path=("a",)
nested_map={"a": {"b": 2}}, path=("a",)
nested_map={"a": {"b": 2}}, path=("a", "b")
  


markdown
Copy code
# Project Title

Brief description of the project.

## Resources

Read or watch:

- [unittest](https://docs.python.org/3/library/unittest.html) — Unit testing framework
- [unittest.mock](https://docs.python.org/3/library/unittest.mock.html) — mock object library
- [How to mock a readonly property with mock?](https://stackoverflow.com/questions/16782112/how-to-mock-a-readonly-property-with-mock)
- [parameterized](https://pypi.org/project/parameterized/)
- Memoization

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- The difference between unit and integration tests.
- Common testing patterns such as mocking, parametrizations, and fixtures.

## Requirements

- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- The first line of all your files should be exactly `#!/usr/bin/env python3`
- A `README.md` file, at the root of the folder of the project, is mandatory
- Your code should use the pycodestyle style (version 2.5)
- All your files must be executable
- All your modules should have documentation (e.g., `python3 -c 'print(__import__("my_module").__doc__)'`)
- All your classes should have documentation (e.g., `python3 -c 'print(__import__("my_module").MyClass.__doc__)'`)
- All your functions (inside and outside a class) should have documentation (e.g., `python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`)
- A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class, or method (the length of it will be verified)
- All your functions and coroutines must be type-annotated.

## Required Files

- utils.py (or download)
- client.py (or download)
- fixtures.py (or download)

## Tasks

### 0. Parameterize a unit test

Familiarize yourself with the `utils.access_nested_map` function and understand its purpose. Play with it in the Python console to make sure you understand.

In this task, you will write the first unit test for `utils.access_nested_map`.

Create a `TestAccessNestedMap` class that inherits from `unittest.TestCase`.

Implement the `TestAccessNestedMap.test_access_nested_map` method to test that the method returns what it is supposed to.

Decorate the method with `@parameterized.expand` to test the function for the given inputs.

```python
nested_map={"a": 1}, path=("a",)
nested_map={"a": {"b": 2}}, path=("a",)
nested_map={"a": {"b": 2}}, path=("a", "b")
For each input, test with assertEqual that the function returns the expected result.

The body of the test method should not be longer than 2 lines.

# Example
def test_access_nested_map(self, nested_map, path):
    self.assertEqual(utils.access_nested_map(nested_map, path), expected_result)


1. Parameterize a unit test
Implement TestAccessNestedMap.test_access_nested_map_exception. Use the assertRaises context manager to test that a KeyError is raised for the given inputs.

2. Mock HTTP calls
Familiarize yourself with the utils.get_json function.

Define the TestGetJson(unittest.TestCase) class and implement the TestGetJson.test_get_json method to test that utils.get_json returns the expected result.

Use unittest.mock.patch to patch requests.get. Ensure it returns a Mock object with a json method that returns test_payload parametrized alongside the test_url.

3. Parameterize and patch
Read about memoization and familiarize yourself with the utils.memoize decorator.

Implement the TestMemoize(unittest.TestCase) class with a test_memoize method.

Inside test_memoize, define a class with a method and a memoized property. Use unittest.mock.patch to mock the method. Test that when calling the property twice, the correct result is returned but the method is only called once.

4. Parameterize and patch as decorators
Familiarize yourself with the client.GithubOrgClient class.

Declare the TestGithubOrgClient(unittest.TestCase) class in a new test_client.py file and implement the test_org method.

Use @patch as a decorator to mock get_json and parametrize the test with a couple of org examples.

5. Mocking a property
Implement the test_public_repos_url method to unit-test GithubOrgClient._public_repos_url.

Use patch as a context manager to mock GithubOrgClient.org and test the result of _public_repos_url based on the mocked payload.

6. More patching
Implement TestGithubOrgClient.test_public_repos to unit-test GithubOrgClient.public_repos.

Use @patch as a decorator to mock get_json and patch as a context manager to mock GithubOrgClient._public_repos_url. Test that the list of repos is what you expect.

7. Parameterize
Implement TestGithubOrgClient.test_has_license to unit-test GithubOrgClient.has_license.

Parametrize the test with given inputs and the expected returned value.

8. Integration test: fixtures
Create the TestIntegrationGithubOrgClient(unittest.TestCase) class and implement setUpClass and tearDownClass.

Use @parameterized_class to parameterize the class with fixtures found in fixtures.py.

The setUpClass should mock requests.get to return example payloads found in the fixtures.

Use patch to mock requests.get(url).json() and return the correct fixtures.

Implement tearDownClass to stop the patcher.


## License

This project is licensed under the terms of the [MIT license](LICENSE).

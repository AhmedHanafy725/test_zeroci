# How to add tests

## Create testing class
This class should inherit from `TestCase` class in unittests.

```python
from unittests import TestCase

class MyTests(TestCase):
    pass
```

## Use fixtures
`TestCase` class has 4 fixtures are freqently used.

### 1- setUpClass
It is class method and running once before all tests.
```python
@classmethod
def setUpClass(cls):
    pass
```

### 2- tearDownClass
It is class method and running once after all tests.
```python
@classmethod
def tearDownClass(cls):
    pass
```

### 3- setUp
It is member method and running before each test.
```python
def setUp(self):
    pass
```

### 4- tearDown
It is member method and running after each test.
```python
def tearDown(self):
    pass
```

## Write a test
### Test name
It should start with `test` followed by test ID, then test name.

### Test description
it should be in the docstring after the test method definition.

### Test scenario
It should be also in the docstring and has the steps for this test.

### Test code
It is should contain the logic of the test.

## Example
1- We have an add method in a module `myadd.py`.

```python
def add(a, b):
    return a + b
```
2- Write the test.
```python
from myadd import add
from unittests import TestCase

class AddTest(TestCase):
    def test01_test_add(self):
        """Test case for adding two numbers
        
        **Test Scenario**
        #. Add two numbers.
        #. Check that the result is the adding of these two numbers.
        """
        #. Add two numbers.
        x = 5
        y = 8
        z = add(x, y)
        
        #. Check that the result is the adding of these two numbers.
        self.assertEqual(z, 13)
```
(**NOTE:** Instead of using comments in the test code, logs can be used for better tracking to the test steps.)


Also pytest fixtures can be used instead of unittests one.

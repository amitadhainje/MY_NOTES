# Pytest Learning Notes

1. Pytest is a framework that makes building and simple and scalable tests easy. It is open-source. 
2. Installing pytest ==> pip install pytest
3. Pytest markers are a powerful feature that allows you to add metadata or labels to your test functions, making it easier to organize and customize your test suite.
3. Fixtures in pytest - Whenever we need to run any code before the test, we use pytest with fixtures. Fixtures are methods in Pytest that provide a fixed baseline for tests to run on top of. A fixture can be used to set up preconditions for a test, provide data, or perform a teardown after a test is finished. They are defined using the @pytest.
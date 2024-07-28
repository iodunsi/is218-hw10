# HW 10

Homework 10 demonstrates the careful approach needed to be successful at developing, as well as the attention to detail that is needed to properly address issues. It highlights the need to isolate a problem, and work specifically towards resolving it. Each branch that is opened to address an individual issue makes it quite easy to take care of just one problem at a time. This is particularly effective when one issue can lead to failure of other tests down the line. This assignment also emphasizes the importance of using pytest for testing specific files and even being able to be more specific by running pytest for the exact tests in questyion. The command “docker compose exec pytest (folder/example.py::name_of_specific_test) saved me a lot of time, compared to running all the pytests at once, something that I’ve admittedly sometimes been guilty of over the last month. 
This assignment also heavily emphasizes documentation. Documentation is especially important when you’re not working individually but rather in a team, because there are plenty of different methods to approach issues and not everyone may think about an issue the same way. Documentation allows you to express yourself and provide insight into your thought process as you identify a bug, as well as working towards solving it. It’s important to be as thorough as possible throughout this process.

The issues that I decided to address go as follows:

[test_create_user_access_denied](https://github.com/iodunsi/is218-hw10/blob/master/tests/test_api/test_users_api.py)

This test was failing (not properly handling permission checks).
1. I reviewed the API endpoint to update error handling for when access is denied.
2. I updated the test to make sure that the proper exception was being raised.


[test_user_base_valid](https://github.com/iodunsi/is218-hw10/blob/master/tests/test_schemas/test_user_schemas.py) - This test failed due to a KeyError, requiring me to make sure that the user_base_data fixture contained all the necessary fields as it was missing “nickname”.

1. I added the nickname field to the fixture.
2. I verified that the test passes with the updated fixture.

[test_create_user_with_valid_data](https://github.com/iodunsi/is218-hw10/blob/master/tests/test_schemas/test_user_schemas.py) - Test was failing because AyncMock was meant to be accessed directly from the unittest.mock library. 

1. I updated the test to properly import and use AyncMock.
2. I verified with pytest that asynchronous functions were being mocked properly and that validation was operating as expected




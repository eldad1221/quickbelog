# Quick using logger

This small project purpose is to add nice and clean logs to your app.
Just import the `quickbelog.Log` class wherever you need and start using it.
To make debugging easier by default it will include the name of the source file and line number in order to understand what code line is responsible for the output.

## Usage:

    from quickbelog import Log

    Log.info(msg='This is an info message')
    Log.debug(msg='This is a debug message')
    Log.warning(msg='This is a warning message')
    Log.error(msg='This is an error message')
    try:
        raise ValueError('Just for testing')
    except ValueError:
        quickbe.Log.exception('Something failed')

## Output

    2022-03-14 15:54:03,411 > INFO  test_logger.py(17) method: test_basic_log_message        This is an info message
    2022-03-14 15:54:03,411 > DEBUG        test_logger.py(21) method: test_debug_message    This is a debug message
    2022-03-14 15:54:03,411 > WARNING      test_logger.py(29) method: test_warning_message          This is a warning message
    2022-03-14 15:54:03,412 > ERROR        test_logger.py(33) method: test_error_message    This is an error message
    2022-03-14 15:54:03,412 > ERROR        test_logger.py(13) method: test_exception_logging        Something failed
    Traceback (most recent call last):
      File ".\test_logger.py", line 11, in test_exception_logging
        raise ValueError('Just for testing')
    ValueError: Just for testing

Have fun :-)
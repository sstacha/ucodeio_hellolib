=====
Hello Library Example
=====

ucodeio_hellolib is a simple example library to test uploading to pypi and installing in a project.

When complete you should be able to:

pip install ucodeio_hellolib

then import and use the output like so:

test_hello.py
-----
::
    import argparse
    from ucodeio_hellolib.hello import get_hello_message

    if __name__ == "__main__":
        parser = argparse.ArgumentParser(description="Print a hello message")
        parser.add_argument("name", nargs='?', type=str, default=None, help="Name to apply to hello message (optional)")
        parser.add_argument("--verbose", "-v", action="store_true", help="verbose output")
        args = parser.parse_args()
        if args.verbose:
            print('verbose: True')
            print(f'name: {args.name}')
        print (get_hello_message(args.name))

To test:
::
    execute python3 -m test_hello

output: hello world
::
    execute python3 -m test_hello steve

output: hello steve

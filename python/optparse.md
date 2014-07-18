

Python `optparse` Cheat Sheet
=============================

Basic usage/flow
----------------

    from optparse import OptionParser

    # Build parser.
    parser = OptionParser(usage="%prog [options] arg1 arg2")

    # Add options here
    parser.add_option(
        "-f", "--file",
        dest="filename", metavar="FILE"
        help="write report to FILE"
    )
    # ...

    # Parse command line arguments
    (options, args) = parser.parse_args()

    # use options.filename, options.verbose


Actions
-------

Default action `store`:

    parser.add_option("-o", dest="filename")

Action `store_true`, `store_false`:

    parser.add_option("-b", action="store_true", dest="background", default=False)
    parser.add_option("-q", action="store_false", dest="verbose", default=True)

Action `store_const`:

    parser.add_option("-d", action="store_const", dest="loglevel", const=DEBUG, default=WARN)

Action `append`:

    parser.add_option("-t", "--tracks", action="append", type="int")


Types
-----

Integer:

    parser.add_option("--repeat", dest="repeat", type="int")


Choice:

    parser.add_option(
        "--output", dest="output",
        type="choice", choices=["html", "json", "xml"]
    )


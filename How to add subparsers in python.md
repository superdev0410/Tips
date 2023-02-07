# How to add subparsers in python

```python
import argparse
import os


def get_args() -> argparse.Namespace:
    """parse command line arguments

    Returns:
        argparse.Namespace: parsed arguments
    """
    
    # define parsers and subparsers
    parser = argparse.ArgumentParser(description="Choose and add files to source folder.")
    subparsers = parser.add_subparsers(dest="command")
    addparser = subparsers.add_parser("add", help="add files to source folder")
    chooseparser = subparsers.add_parser("choose", help="choose files and copy to anohter folder")

    # add arguments to addparser
    addparser.add_argument("files", nargs="+", help="list of filepaths to add")

    # add arguments to chooseparser
    chooseparser.add_argument(
        "-n", "--num", 
        type=int, 
        help="number of files to choose", 
        default=50
    )
    chooseparser.add_argument(
        "-d", "--destination",
        help="destination folder path",
        default="E:\MyProgram\Screenshot\Source"
    )
    
    return parser.parse_args()


def main():
    """
    main function
    """

    # parse command-line arguments
    args = get_args()
    if args.command == "add":
        # do action
        pass
    elif args.command == "choose":
        # do action
        pass
    

if __name__ == "__main__":
    main()
```
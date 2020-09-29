# Static Site Generator written in Python

Use `sitegen` to generate static websites (plain html files with little to no server-side interaction) from MarkDown text files (.md).

## Installation

`sitegen` requires `python-markdown` to work. To install it, either run:

    pip install markdown

Or use your system's package manager. The `pip` solution is easy, unobtrusive and doesn't require root access, though.

Afterwards simply clone this repository, then place `sitegen` in your executable path.

    git clone https://github.com/kzimmermann/static-sitegen
    cd src
    sudo cp sitegen /usr/local/bin # or similar path

## Usage

You must provide am HTML template file and specify it in `sitegen` itself. To do so, find this line and edit it to point to your template:

    TEMPLATE = "/path/to/your/template.html"

The template file must contain exactly two "holes" on it, specified as the Pythonic substitution string `%s`. The first one must be included between the `<title></title>` tags in Head, the other one is for your main content, somewhere within your `<body>`. 

Something like this, for example, works:

    <html>
        <head>
            <title>%s - my little zany website</title>
            <meta charset="utf=8" />
            <!-- add whatever else you want, CSS, Favicon, meta... -->
        </head>
        <body>
            <!-- header, navigation bar, etc to taste... -->

            %s

            <!-- footer, scripts, etc... -->
        </body>
    </html>

You can also see my `template_example.html` file to get a grasp of how it works.

## Disclaimer

This is alpha-quality software and is not always guaranteed to work. I wrote it mostly for my own exercise since `bash` proved to be quite cumbersome for the task. There are probably many others out there much better suited, such as Jekyll.

Please let me know of any bugs, though.

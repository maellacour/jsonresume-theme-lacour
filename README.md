# Custom JSONResume Theme: Lacour

A theme for JSONResume, leveraging Bootstrap and FontAwesome for styling. It was initially based on [LinuxBozo's theme](https://github.com/LinuxBozo) and has been modified to better fit specific needs, particularly in the header and section displays.

The theme is primarily in English. For a French version, please refer to the `french` branch.

## Requirements

* **[resumed](https://github.com/rbardini/resumed):** The command-line tool for JSONResume.
* **(Optional) [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html):** For converting your HTML resume to PDF.

## Getting Started

1. **Ensure `resumed` is installed.** If you haven't installed it yet, you can typically do so via npm:

    ```bash
    npm install -g resumed
    ```

2. **Use the theme with `resumed` to generate your resume.**
    If you have your `resume.json` file and this theme in the current directory (e.g., after cloning this theme repository), you can run:

    ```bash
    resumed render resume.json --theme . -o out/resume.html
    ```

    Or, if your `resume.json` is in a different location:

    ```bash
    resumed render path/to/your/resume.json --theme path/to/this/theme -o out/resume.html
    ```

    This will generate an HTML version of your resume in the `out` directory.

### Exporting to PDF

To convert the generated `out/resume.html` to a PDF file using `wkhtmltopdf`, run the following command:

```bash
wkhtmltopdf --enable-local-file-access -B 0 -L 0 -R 0 -T 0 -d 300 --viewport-size 1980 resume.html resume.pdf
```

## Features & Customization

### Social Profiles

This theme displays social network links from your `resume.json` file, specifically from the `basics.profiles` array.

**Supported Profiles:**

* Facebook
* Github
* Twitter
* Google Plus
* YouTube
* Vimeo
* Linkedin
* Pinterest
* Flickr
* Behance
* Dribbble
* CodePen
* Soundcloud
* Steam
* Reddit
* Tumblr
* Stack Overflow
* Bitbucket
* Gitlab

**Important Notes:**

* All profile entries in your `resume.json` are optional.
* The `network` field for each profile in `basics.profiles` (e.g., "Github", "Twitter") **must be entered without spaces**.
* If a specific icon isn't predefined for a profile you've listed, the theme will attempt to use the corresponding `-square` version of the icon from FontAwesome.
* For optimal mobile-friendliness, it's advisable to limit the number of displayed profiles to approximately 10.

### Optional Sections

All standard resume sections (e.g., work, education, skills, publications, etc.) are optional. If a particular section is not included in your `resume.json` file, it will simply not appear in the rendered resume.

## Issues & Contributions

If you encounter any problems with this theme or have suggestions for improvement, please feel free to open an issue on the project's repository.
Contributions, such as adding support for more social networks or other enhancements, are also welcome via pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

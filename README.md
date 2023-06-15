# Red Hat OpenShift Data Science Quick Course

Welcome to the OpenShift Data Science quick course!. This course uses standard asciidoc for content authoring that is then rendered to HTML and hosted by GitHub Pages. It uses the Antora publishing platform (https://antora.org) to transform the asciidoc conent to HTML.

To contribute, you can use locally installed tooling on your workstation, or you can use OpenShift DevSpaces to work with content using a web based IDE without the need to install anything.

## Locally installed Tooling

1. Install an LTS version of the Node.js runtime on your workstation.
2. Clone this Git repository to a folder of your choice.
3. Install an editor of your choice. We recommend Visual Studio Code with the *asciidoctor* plug-in.
4. Follow the steps in the *Previewing HTML content and publishing* section. All the directory paths are relative to the root location where the repository is cloned.

## The "Easy Button" aka OpenShift DevSpaces

1. To open and edit the asciidoc files in OpenShift DevSpaces, click <a href="https://devspaces.apps.cluster-bqmpk.bqmpk.sandbox1618.opentlc.com/#https://github.com/RedHatTraining/rhods-quick-course" target="_blank">here</a>, and log in using your provided OpenShift credentials:

2. If you launch the DevSpaces workspace for the first time, it will take a few minutes to download the container image, clone the Git repository, and set up your project. All the required tooling and IDE plugins are automatically installed and set up for you.

3. Follow the steps in the *Previewing HTML content and publishing* section. All the directory paths are relative to the root location where the repository is cloned.

## Previewing HTML content and publishing

1. Launch the VSCode terminal (Press **Ctrl + `**). All commands in the following steps are to be run from the root of the directory where you cloned the repository. If you are using the web-based OpenShift DevSpaces IDE, you must already be in the root of the repository.

2. Run **npm install** to install the Node.js dependencies for the project.

```bash
$ npm install
```

3. The Git repository contains the default chapter and section stubs with comments from the product owner/architect to help guide you. Inspect the *antora.yml* file, which defines the top level modules (chapters) in this course. 

4. The starting point (index page) for the course is rendered from asciidoc content in the *modules/ROOT/pages/index.adoc* file.

5. Each top level module has a separate asciidoc file (*nav.adoc*) located in *modules/module_name/* folder. The *nav.adoc* lists the sections that make up the chapter/module.

6. Edit the asciidoc files under *modules/module_name/pages* folder for writing lectures and hands-on lab content as per the outline provided by the course architect/peoduct owner. You can use the *asciidoctor* plug-in preview plugin (Press *"Ctrl + Shift + V"* in VSCode) to preview the rendered HTML content.

7. To preview the rendered website as it would look for end-users consuming this content, do the following:

    * Run the **npm run watch:adoc** command to automatically detect changes to your asciidoc content and invoke the Antora HTML generator:

    ```bash
    $ npm run watch:adoc
    ```

    * In another termainal window, run the **npm run serve** command that starts a local web server that serves the generated HTML content:

    ```bash
    $ npm run serve
    ```
    You will be shown the local URL where you can view the rendered content. Open the link in a web browser.

    * Keep making changes in your asciidoc source files. The **npm watch** command will automatically detect your changes and re-generate the HTML content. Refresh your web browser to view the updated content

8. Once you are satisfied with how the HTML content is rendered locally in your workspace, you can commit your changes and do a **git push** to push your content to the **main** branch of the course Git repository. An automated GitHub action runs on every push to the **main** branch and updates the HTML content in GitHub Pages.

9. After a few minutes, the GitHub action finishes and you can view the latest rendered asciidoc content at https://redhattraining.github.io/rhods-quick-course.

10. If you run into any issues, report bugs/suggestions/improvements about this course here - https://github.com/RedhatTraining/rhods-quick-course/issues

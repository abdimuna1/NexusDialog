NexusDialog
===========
**Quick and Simple Forms for Android**

NexusDialog is a framework that allows you to easily and quickly create forms in Android with little code. It's great
for apps having many form-based screens, since it reduces the boilerplate code to setup the view layout and tying things
together in the Activity. Currently, it supports Android API 10+

This library follows [semantic versioning](http://semver.org/). Note that since this library is still active in
development, new releases might introduce interface-breaking changes, which will be indicated in the changelog.
NexusDialog 1.0.0 will be the first stable release.

A Simple Example
----------------
To give you an idea of the simplicity of NexusDialog, here's a screenshot of a simple example:

[screenshot]

Here's the code for that example (less than 7 lines of code!):

    import java.util.Arrays;
    import com.github.dkharrat.nexusdialog.FormActivity;
    import com.github.dkharrat.nexusdialog.controllers.*;

    public class SimpleExample extends FormActivity {

        @Override protected void initForm() {
            FormSectionController section = new FormSectionController(this, "Personal Info");
            section.addElement(new EditTextController(this, "firstName", "First name"));
            section.addElement(new EditTextController(this, "lastName", "Last name"));
            section.addElement(new SelectionController(this, "gender", "Gender", true, "Select", Arrays.asList("Male", "Female"), true));

            addSection(section);

            setTitle("Simple Example");
        }
    }

For more examples, browse the [samples](http://github.com/dkharrat/nexusdialog/samples) directory.

Features
--------
NexusDialog supports many built-in fields for your form, like text boxes, date pickers, spinners, etc. The framework is
also designed to be extensible so that you can easily add custom form elements if needed. Contributions are also
welcome! If you've implemented a custom control that is useful, pull requests are welcome and appreciated! Currently,
the following form elements are supported:

* **EditTextController**: EditText view that allows for free-form text input.
* **DatePickerController**: Displays a date picker to allow choosing a specific date
* **SelectionController**: Displays a spinner with a list of item to select from
* **SearchableSelectionController**: Displays a (typically large) list of items to select from, with the ability to
    search the list and also allow free-form text.

Apps Using NexusData
--------------------
Do you have an app that's utilizing NexusData? [Let me know](mailto:dkharrat@gmail.com) and I'll add a link to it here!

Planned Features
----------------
The framework is constantly being improved and new features are being implemented. The following improvements are
planned:

* Support switches (on/off)
* Support buttons
* Support secure text for EditTextController
* Support sliders
* Allow disabling free-form text in SearchableSelectionController
* Make label text optional for labeled fields

How to Add NexusDialog to Your Project
--------------------------------------
There are multiple ways to include your project, depending on your build environment:

#### Gradle

Add the following dependency to your build.gradle file for your project:

    dependencies {
      compile 'com.github.dkharrat.nexusdialog:nexusdialog:0.1.0'
    }

#### Maven

Add the following dependency to your pom.xml file for your project (requires android-maven-plugin 3.8.0+):

    <dependency>
        <groupId>com.github.dkharrat.nexusdialog</groupId>
        <artifactId>nexusdialog</artifactId>
        <version>0.1.0</version>
        <type>aar</type>
    </dependency>

#### Android Studio or IntelliJ 13+

Add the appropriate dependency in your build.gradle file and refresh your project.

#### Eclipse
1. In Eclipse, import the android-support-v7-appcompat library by following the instructions at
   [this page](http://developer.android.com/tools/support-library/setup.html#libs-with-res).
2. Ensure the android-support-v7-appcompat library has been imported and is compiling without errors.
3. Import the nexusdialog library project into Eclipse:
   1. Select **Existing Android Code Into Workspace** and click **Next**.
   2. Browse to the library path: nexusdialog/src/main.
   3. Click **Finish** to import the project. You should now see a project called _main_.
   4. Right-click on the project in the Package Explorer and select **Refactor > Rename**.
   5. Name the project 'nexusdialog'
   6. Right-click the _nexusdialog_ project in the Package Explorer and select **Properties**.
   7. Select the **Java Build Path** page and click on the **Source** tab.
   8. Remove the **nexusdialog/src** source folder from the list.
   9. Click on the **Add Folder** button.
   10. Select the folder _java_ and click **OK**.
   11. In the same **Properties** dialog, select the **Android** page.
   12. Under the **Project Build Target** select a target of API 17 or higher.
   13. Enable the **Is Library** checkbox.
   14. Click on the **Add** button to add a library dependency.
   15. Select the _android-support-v7-appcompat_ library and click **OK**.
   16. Press **OK** in the **Properties** dialog to close it.
   17. Ensure the library compiles without errors. You may need to clean the project multiple times to be in a clean state.
4. Add the _nexusdialog_ project as a dependency to your project:
   1. Right-click on your project in the Package Explorer list and select **Properties**.
   2. Select the **Android** page.
   3. Under the Library section, click the **Add** button.
   4. Select _nexusdialog_ and press **OK**.
   5. Press **OK** in the **Properties** dialog to close it.
5. You can now start using NexusDialog in your project.

How to Use NexusDialog
----------------------
TODO

Documentation
-------------
See the current [Javadoc](javadoc)

Styling
-------
TODO

Adding Custom Elements
----------------------
TODO

Creating IntelliJ project
-------------------------

1. gradle idea
2. open project in IntelliJ
3. Right click on root level project and click on 'Open Module Settings'
4. Project --> Project SDK: "Adnroid 4.x.x Platform"
5. Modules --> Modules SDK: "Android 4.x.x Platform"
6. Modules --> Click on '+' --> 'Import Module'
7. Select 'nexusdialog' directory and click 'OK'
8. Select 'Create module from existing source'
9. Click on 'Unmark All' button
10. Select "/.../nexusdialog/src/main" directory and click 'Next'
11. Click 'Finish'
12. Under 'main' module, change Name to 'lib'
13. Remove "/.../nexusdialog/src/main" content root by clicking on 'x' beside it, and click 'Yes' to confirm
14. Click on 'Add Content Root' button
15. Select the 'nexusdialog' directory and click 'OK'
16. Under the Content Root, remove all 'Source Folders' except "src/main/gen"
17. Under the directory tree on the right, select the 'java' directory under 'src/main'
18. Click the 'Sources' button above
19. Click the 'Android' item under the 'lib' module and check the 'Library module' checkbox
20. Click 'OK' to close the Project Structure dialog

Contributing
------------
Contributions via pull requests are welcome! For suggestions, feedback, or feature requests, please submit an issue.

Author
------------
Dia Kharrat - dkharrat@gmail.com
Twitter: http://twitter.com/dkharrat

License
-------
    Copyright 2013 Dia Kharrat

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

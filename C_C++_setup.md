# C/C++ Setup for Visual Studio Code

This guide will walk you through setting up C/C++ for use with Visual Studio Code. Follow each instruction carefully.

---


## **1. Install `MinGW` Compiler:**

Download and Install the **MinGW** compiler from any of the following links:

* ➤ [Link 1](https://drive.google.com/file/d/1aC9xQL2J1JSMT-ChEd2DP4OR4es5FSjq/view)
* ➤ [Link 2](https://drive.google.com/file/d/1KqDL7maNwhqBF34HFAKhCKnRDwepEqn7/view)
* ➤ [Link 3](https://sourceforge.net/projects/mingw-w64/)

After installation, proceed to the next step.

---

## **2. Copy Path:**

* After installing MinGW, go to the **folder** where it was installed on your PC.
* Open the `bin` folder within the MinGW folder
  * (like-> ***C:\MinGW\bin***).
* `Copy the path` of this **bin** folder.



## **3. Set Environment Variables:**
* Open the Windows search box (Windows key + S).
* Search for `edit the system environment variables` and **open** it.
* Click the `Environment Variables` button.
* In the **"System variables"** section, double-click on the **`Path`**.
* Click **`New`**.
* **`Paste`** the path you copied earlier (the path to the MinGW `bin` folder).
* Click **`OK`** on all open windows to save the changes.


---


## **4. Install Git Bash:**

* Download the Git Bash *`standalone installer`* from the following link:
```
    https://git-scm.com/downloads
```
* Run the downloaded installer and follow the on-screen instructions to install Git Bash on your system.


---


## **5. Install VS Code Extensions:**

* Open **Visual Studio Code**.
* Go to `Extensions` (Ctrl+Shift+X)
* **Search** for the following extensions and install then one-by-one:
    * `C/C++ Extension Pack`
    * `Code Runner`


---


## **6. Code-Runner extension setup:**

* Open the `Code-Runner` extension in VS Code.
    <!-- * Click on the "Manage" icon (gear icon) in the bottom-left corner of VS Code. -->
* Go to the "**Settings**" of code-runner extension.
* Scroll a little & search for **"code-runner: executor map**"
* Click `Edit in settings.json`.
* Here, **Copy** and **Paste** the following JSON & Save it:

```json
{
  "C_Cpp.default.cppStandard": "c++20",
  "C_Cpp.default.cStandard": "c11",
  "terminal.integrated.defaultProfile.windows": "Git Bash",
  "code-runner.runInTerminal": true,
  "code-runner.saveAllFilesBeforeRun": true,
  "code-runner.terminalRoot": "/",
  "code-runner.executorMapByGlob": {
    "pom.xml": "cd $dir && mvn clean package"
  },

  "code-runner.executorMap": {

  
    "javascript": "node",
    "java": "cd $dir && javac $fileName && java $fileNameWithoutExt",
    "zig": "zig run",
    "objective-c": "cd $dir && gcc -framework Cocoa $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "php": "php",
    "python": "python -u",
    "perl": "perl",
    "perl6": "perl6",
    "ruby": "ruby",
    "go": "go run",
    "lua": "lua",
    "groovy": "groovy",
    "powershell": "powershell -ExecutionPolicy ByPass -File",
    "bat": "cmd /c",
    "shellscript": "bash",
    "fsharp": "fsi",
    "csharp": "scriptcs",
    "vbscript": "cscript //Nologo",
    "typescript": "ts-node",
    "coffeescript": "coffee",
    "scala": "scala",
    "swift": "swift",
    "julia": "julia",
    "crystal": "crystal",
    "ocaml": "ocaml",
    "r": "Rscript",
    "applescript": "osascript",
    "clojure": "lein exec",
    "haxe": "haxe --cwd $dirWithoutTrailingSlash --run $fileNameWithoutExt",
    "rust": "cd $dir && rustc $fileName && $dir$fileNameWithoutExt",
    "racket": "racket",
    "scheme": "csi -script",
    "ahk": "autohotkey",
    "autoit": "autoit3",
    "dart": "dart",
    "pascal": "cd $dir && fpc $fileName && $dir$fileNameWithoutExt",
    "d": "cd $dir && dmd $fileName && $dir$fileNameWithoutExt",
    "haskell": "runghc",
    "nim": "nim compile --verbosity:0 --hints:off --run",
    "lisp": "sbcl --script",
    "kit": "kitc --run",
    "v": "v run",
    "sass": "sass --style expanded",
    "scss": "scss --style expanded",
    "less": "cd $dir && lessc $fileName $fileNameWithoutExt.css",
    "FortranFreeForm": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran-modern": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran_fixed-form": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "sml": "cd $dir && sml $fileName",


    // ~~ Output in Terminal for C/C++
    // "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt.exe && $dir$fileNameWithoutExt.exe",
    // "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt.exe && $dir$fileNameWithoutExt.exe",


    // ~~Output in Text file for C/C++
    "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt.exe && timeout 15s $dir$fileNameWithoutExt.exe < input.txt > output.txt || (echo -n > output.txt && echo 'Time Limit Gone')",
    "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt.exe && timeout 15s $dir$fileNameWithoutExt.exe < input.txt > output.txt || (echo -n > output.txt && echo 'Time Limit Gone')",
  },




  "terminal.integrated.focusAfterRun": "terminal",
  "editor.mouseWheelZoom": true,
  "terminal.integrated.mouseWheelZoom": true,
  // "editor.wordWrap": "on",
  "terminal.integrated.cursorBlinking": true,
  "explorer.confirmDragAndDrop": false,
  "liveServer.settings.donotShowInfoMsg": true,
  "liveServer.settings.donotVerifyTags": true,
  "redhat.telemetry.enabled": true,
  "explorer.confirmDelete": false,
  "java.debug.settings.onBuildFailureProceed": true,
  "security.workspace.trust.untrustedFiles": "open",
  "codesnap.boxShadow": "rgba(0, 0, 0, 0.55) 0px 10px 68px",
  "codesnap.containerPadding": "1em",
  "workbench.startupEditor": "none",
  "git.openRepositoryInParentFolders": "always",
  "editor.linkedEditing": true,
  "terminal.integrated.shellIntegration.enabled": false,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.cursorBlinking": "expand",
  "editor.bracketPairColorization.enabled": true,
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 100,
  "editor.minimap.renderCharacters": false,

  
  "workbench.editorAssociations": {
    "*.jar": "default"
  },
  "files.associations": {
    "iostream": "cpp"
  },
  "java.project.referencedLibraries": [
    "lib/mysql-connector-j-9.1.0.jar"
  ],
  "settingsSync.ignoredExtensions": [
    
  ],
  "workbench.editor.empty.hint": "hidden",
  "workbench.colorTheme": "Learn with Sumit Theme - Dracula version",
  "workbench.iconTheme": "material-icon-theme",
  "terminal.integrated.fontSize": 19,
  
}
```


---

### ✅ C/C++ is now ready to use with VS Code!


---
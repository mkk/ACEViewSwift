# ACEViewSwift

Use the wonderful [ACE editor](http://ace.ajax.org/) in your Swift Cocoa applications.

![ACEView example](Screenshots/Demo Window.png)

For great justice.

# Documentation

Most of the APIs are already properly documented and available through Xcode's quick documentation, but a proper documentation is coming soon :)

# Usage

1. Clone the repo
2. Run `git submodule update --init --recursive` (for the dependencies)
3. Build the framework target
4. Add it into your Swift project
5. `import ACEViewSwift` into your files in order to use it

*Note*: A pod will be released soon to simplify installation

![ACEView XIB](https://raw.github.com/faceleg/ACEView/master/Collateral/ace-xib.jpg)

Make sure you've got an IBOutlet in your view controller, and bind that bad girl:

![ACEView XIB Binding](https://raw.github.com/faceleg/ACEView/master/Collateral/ace-xib-binding.jpg)

Now, you could do something like this:

```Swift
import Cocoa
import ACEViewSwift

class ViewController: NSViewController {

  @IBOutlet weak var aceView: ACEView!

  override func viewDidLoad() {
      super.viewDidLoad()

      // Some text content
      let html = "..."

      // onReady() is a convenience closure for configuring
      // the ACEView right after it has been finished loading

      aceView.onReady = { [unowned self] in
          self.aceView.string = html
          self.aceView.mode = .HTML
          self.aceView.theme = .Xcode
          self.aceView.keyboardHandler = .Ace
          self.aceView.showPrintMargin = true
          self.aceView.showInvisibles = false
          self.aceView.basicAutoCompletion = true
          self.aceView.liveAutocompletion = true
          self.aceView.snippets = true
          self.aceView.emmet = true
          self.aceView.focus()
      }
  }

}

```

# Contributions

All are welcome, all are read.

Many thanks to [Michael Robinson](https://github.com/faceleg) and all the people that developed the [original ObjC framework](https://github.com/ACENative/ACEView) !

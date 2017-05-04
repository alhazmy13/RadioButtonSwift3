# RadioButtonSwift3

# How to use
* Put some UIButtons onto a View and change the UIButtons' type to "custom".
* Set the UIButtons' class to "RadioButton"
* To customize the button, simply set properties directly in Interface Builder

# Code Example 
```swift


    @IBOutlet weak var radioButton1: RadioButton!
    @IBOutlet weak var radioButton2: RadioButton!
    
    lazy var radioButtons: [RadioButton] = {
        return [
            self.radioButton1,
            self.radioButton2,
        ]
    }()
    

    @IBAction func onRadioButton1Clicked(_ sender: RadioButton) {
        updateRadioButton(sender)
    }
    @IBAction func onRadioButton2Clicked(_ sender: RadioButton) {
         updateRadioButton(sender)
    }
    

    // MAIN Methodes
    func updateRadioButton(_ sender: RadioButton){
        radioButtons.forEach { $0.isSelected = false }
        sender.isSelected = !sender.isSelected

    }
    
    func getSelectedRadioButton() -> RadioButton? {
        var radioButton: RadioButton?
         radioButtons.forEach { if($0.isSelected){ radioButton =  $0 } }
        return radioButton
    }

 ```
# CCTextField

Forked from @ignacioinglese - thanks for the very nice solution!

A few new notes:

Create the whole CCTextField on it's own.  There is an issue with creating items seperate.

Then add it to your CCLayer, CCSprite, etc… it's wisely inherited from CCNode. Position, scale, etc… as needed.  It makes a UITextField off screen, and then updates keyed input to a CCLabelTTF.  Brilliant!

Example:

CCTextField *tf = [CCTextField textFieldWithFieldSize:CGSizeMake(400, 100) fontName:@"Arial" andFontSize:32];
CCSprite *mySprite = [CCSprite alloc]init];
tf.
[mySprite addChild:tf]



Original Readme
==========


CCTextField is a cocos2d-based implementation for text input.
I found myself having to deal with UITextFields that stayed on top of my UI no matter what happened below and decided to create this.

There are basically two ways to create a CCTextField.

    // Create the CCTextField from some UITextField and a CCLabelTTF (several CCTextFields can share the same UITextField this way)
    UITextField * someField = [[UITextField alloc] initWithFrame:CGRectMake(2000, 200, 150, 50)]; // Make sure it's not visible
    // Set any attributes to your field
    
    CCLabelTTF * someLabel = [CCLabelTTF labelWithString:@"" dimensions:textFieldSize alignment:UITextAlignmentLeft fontName:fontName fontSize:fontSize];

    // Finally
    CCTextField * tf = [CCTextField textFieldWithLabel:someLabel andTextField:someField];

    // or...

    // Create the whole CCTextField on it's own
    CCTextField * tf = [CCTextField textFieldWithFieldSize:CGSizeMake(someWidth, someHeight) fontName:fontName andFontSize:fontSize];

If you choose to create your CCTextField on it's own, you can change any of it's UITextField properties (such as keyboard type, return key) just by calling those selectors on it, and they will be forwarded to the inner UITextField.


If you find this class helpful, I'd love to hear about it. Drop me a line @ignacioinglese.

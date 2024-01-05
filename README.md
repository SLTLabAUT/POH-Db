# 📝 POH-Db

Persian Online Handwriting Database (POH-Db) is a dataset for unconstraint Persian online handwriting collected using https://FarsiHandwriting.ir/.

A new version of the dataset is released approximately every six months.

If you want to access the dataset under a different license, you should consider contacting POH-Db authors.

## 🤝 How to Contribute

First of all, thanks for taking the time to contribute! The success of crowdsourcing projects would not be possible without the contribution of people like you.

To contribute, you should visit the https://FarsiHandwriting.ir/ website, and after registration, you can donate your handwriting to proceed technologies in Persian handwriting recognition.

To contribute to the collection web app, you can consider creating PRs for the [OnHandCollect](https://github.com/SLTLabAUT/OnHandCollect) repository. We encourage people to help us create a semi-automatic segmentation system to segment writepad's ground truth labels to line and word levels.

## 📜 About the Dataset

The folder structure of the dataset is as follow:

-   GroundTruths
-   Writepads
-   Writers

### Ground Truths

We have used selected phrases from Bijankhan's corpus and Farsi Wikipedia as the ground truths. They are chosen in such a way that has a normal distribution in terms of word counts and includes most of the three consecutive characters in Persian. These ground truths consist of the Persian alphabet and punctuations, but there are no numbers in this version.

Ground truths are saved in a simple custom [XML](https://w3.org/XML/) format.

![Text - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/Text%20-%20XML.png)

![WordGroup - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/WordGroup%20-%20XML.png)

![WordGroup2 - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/WordGroup2%20-%20XML.png)

![WordGroup3 - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/WordGroup3%20-%20XML.png)

![NumberGroup - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/NumberGroup%20-%20XML.png)

### Writepads

Each handwriting sample is named a Writepad. There are three types of writepads:

-   Text: A few sentences with an average of 16 words.
-   WordGroup: 4-10 lines with an average of 7 lines, each containing 1 word.
-   WordGroup2: lines containing groups of 2 words.
-   WordGroup3: lines containing groups of 3 words.
-   NumberGroup: 14 lines of decimal numbers with basic mathematical symbols.
-   Sign (Not public): Signature.

Writepads are saved in [InkML](https://w3.org/TR/InkML/) format and contain the following properties for each point recorded (Some data may be unavailable based on the user's device):

-   X and Y positions
-   Time
-   Pressure
-   Tangential Pressure
-   Pointer Width and Height
-   Tilt X and Y
-   Twist

Each property mentioned above has some metadata description in every InkML file. These properties are defined inside `<traceFormat>` tag.

Other metadata related to each writepad is defined in `<annotationXML>` tag and contains the following properties:

-   Writer ID
-   Pointer Type (Input)
-   Writepad Type
-   Hand
-   Ground Truth ID

Writepads' ground truths are specified on writepad-level.

Sign writepads are not publicly available and are only accessible for official authorities. To access Sign writepads, you should consider contacting POH-Db authors.

![Writepad - InkML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/Writepad%20-%20InkML.png)

### Writers

Writers' metadata are also saved in a simple [XML](https://w3.org/XML/) format. It contains the following properties:

-   Sex
-   Handedness
-   Education
-   Birth Year

![Writer - XML](https://github.com/SLTLabAUT/POH-Db/blob/main/assets/Writer%20-%20XML.png)

### How to Start Using the Dataset

For now, a simple model named RetardOHR has used the dataset. It uses only X, Y, and Time for feature extraction. Reading its source code would be a good starting point.

## 🔗 References

-   [OnHandCollect](https://github.com/SLTLabAUT/OnHandCollect)
-   [RetardOHR](https://github.com/SSgumS/RetardOHR)
-   Bijankhan, Mahmood, Sheykhzadegan, Javad, Bahrani, Mohammad, and Ghayoomi, Masood. Lessons from building a Persian written corpus: Peykare. Language resources and evaluation, 45(2):143–164, 2011.
-   https://w3c.github.io/pointerevents/
-   https://w3.org/TR/InkML/
-   https://w3.org/XML/

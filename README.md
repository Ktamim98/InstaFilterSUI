# InstaFilter
InstaFilter is an iOS application that allows you to apply various filters to images and save them to your photo album.

This app is built using SwiftUI and Core Image frameworks. It uses the ImagePicker component to allow the user to select an image from their photo library, and then it applies filters to the image using CIFilters.

## How to Use
To use the app, simply tap the image area to select a picture from your library. Then you can adjust the filter intensity using the slider and choose a filter from the filter sheet. Once you have applied the desired filter, you can save the filtered image to your photo album using the save button.

## Implementation
- The app is implemented using the SwiftUI framework, and it uses the CoreImage and PhotosUI frameworks to perform image processing and to interact with the user's photo library.

- The ContentView struct defines the main view of the app. It contains several @State properties that store the current state of the app, such as the input image, the processed image, the current filter, and the filter intensity.

- The body property of the ContentView struct defines the user interface of the app. It consists of a VStack that contains a ZStack with a Rectangle and a Text view that display the selected image, a Slider that controls the filter intensity, and two buttons that allow the user to change the filter and save the processed image.

- The applyProcessing() method applies the current filter to the input image using the CoreImage framework. It first checks the input keys of the filter to determine which filter parameters should be set based on the current filter intensity. It then creates a CIImage from the output of the filter, converts it to a UIImage, and updates the image and processedImage @State properties.

- The loadImage() method loads the input image into the app and applies the current filter to it by calling the applyProcessing() method.

- The save() method saves the processed image to the user's photo library using the ImageSaver class.

- The setFilter(_:) method sets the current filter to the given filter, loads the input image, and applies the current filter to it.

- The ImagePicker struct defines a view that allows the user to select an image from their photo library. It uses the PHPickerViewController from the PhotosUI framework to display the photo library.

- The ImageSaver class provides a method for saving an image to the user's photo library. It uses the UIImageWriteToSavedPhotosAlbum method to save the image. It also defines two closure properties that are called when the save operation is completed, either successfully or with an error.

## Acknowledgements
InstaFilter was created as part of the 100 Days of SwiftUI course by Paul Hudson.

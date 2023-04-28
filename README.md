# Rhfiles

Rhfiles is a Flutter package that provides a simple and easy-to-use file picker with a built-in UI. With Rhfiles, you can quickly integrate file selection functionality into your Flutter application and get a list of selected files. Rhfiles supports picking files from the device's file system, camera, gallery, and URL.
RhUtils is there which has all the pick functionalities with compressor, cropper, etc.

## Features

- Supports file picking from the device's file system, camera, gallery, and URL.
- Provides a built-in UI for file selection.
- Allows customization of UI elements.
- File compressor for compressing image and video files with quality controls.
- Image cropper for cropping of image files.

## Installation

Add the following line to your `pubspec.yaml` file:

```yaml
dependencies:
  rhythm_files: ^1.0.0
```

## Usage

### RhFiles
```dart
final RhFiles rhFiles = RhFiles.instance;

List<File?> pickedFiles = await rhFiles.pick(
  source: Source.file,
  allowMultiple: true,
  fileType: FileType.custom,
  allowedExtensions: ['jpg', 'png'],
);

rhFiles.dashboard(
  onPick: (list) {
    files = list;
    setState(() {});
  },
),
```

### RhUtils
```dart
final RhUtils utils = RhUtils.instance;

List<File?> files = await utils.pickFilesFromDevice(
  allowMultiple: true,
  fileType: FileType.custom,
  allowedExtensions: ['jpg', 'jpeg', 'png'],
);

File? croppedImage = await utils.cropImage(
  imageFile: File('path/to/image.jpg'),
  context: context,
);

File? compressedFile = await RhUtils.instance.compressFile(
  file: originalFile, // an image or video
);

File? compressedFile = await RhUtils.instance.compressImage(image: imageFile, quality: 80, percentage: 50);

File? compressedVideo = await RhUtils.instance.compressVideo(
  video: File('/path/to/video.mp4'),
  videoQuality: RhVideoQuality.MediumQuality,
  deleteOrigin: true,
  includeAudio: false,
  frameRate: 30,
  duration: 60,
);
```


|![Sample Image](https://images.pexels.com/photos/1181675/pexels-photo-1181675.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1) | [![Sample video](https://q5n8c8q9.rocketcdn.me/wp-content/uploads/2019/09/YouTube-thumbnail-size-guide-best-practices-top-examples.png.webp)](http://techslides.com/demos/sample-videos/small.mp4) |
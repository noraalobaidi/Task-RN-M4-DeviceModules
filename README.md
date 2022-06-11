# OCR App 📷

## Instructions

- Fork and clone [this repository](https://github.com/JoinCODED/Task-RN-M4-DeviceModules) to your `Development` folder.

### Picking the image

1. Install the dependencies:

   ```bash
   expo install expo-image-picker
   ```

2. Import `ImagePicker` from `@react-native-community/image-picker`:

```js
import * as ImagePicker from 'expo-image-picker';
```

3. Create a state that will hold the image.
4. Set the initial state of the image to `https://cdn.sick.com/media/ZOOM/2/82/782/IM0077782.png`.
5. Create a state that will hold the text.
6. Set the initial state of the text to `Pick an image`.
7. In your `handleOcr` function, call `ImagePicker.launchImageLibraryAsync` to open the image picker.
8. Use `await` because this method is asynchronous.
9. Store the result in a variable called `result`.
10. `result` can have two properties: `cancelled` and `uri`. Check if the user has not cancelled the picker, the set the image to the image picked by the user using `result.uri`.

[docs imagePicker](https://docs.expo.io/versions/latest/sdk/imagepicker/)

### Sending the image to the server

1. Install the dependencies:

   ```bash
   import * as FileSystem from 'expo-file-system';
   ```

2. Import `FileSystem` from `expo-file-system`:

```js
import * as FileSystem from 'expo-file-system';
```

3. Import `FileSystemUploadType` from `expo-file-system`:

```js
import { FileSystemUploadType } from 'expo-file-system';
```

4. Use those two modules to send your image to the server (DO NOT USE AXIOS).

5. When accessing the `localhost` from the emulator, you need to replace the word `localhost` with the IP address of your computer.

Google this: `How to get the IPv4 address windows/mac`

6. The result of `FileSystem.uploadAsync` will be in a property called `body`.
7. Set the `text` to the body of the response.

[docs uploadAsync](https://docs.expo.dev/versions/latest/sdk/filesystem/#filesystemuploadasyncurl-fileuri-options)

### 🍋 Check Internet Connection

    1. Import `Network` from `expo-network`.
    2. At the top of your `handleOcr` function, check if the user is connected to the internet.
    3. If he's not connected, set the text to `No internet connection and return.

[docs network](https://docs.expo.io/versions/latest/sdk/network/)

[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/1.%20Singlish%20to%20Sinhala%20Text%20Conversion/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/3.%20Sinhala%20Grammar%20Conversion/README.md)

# Sinhala Audio to Text Conversion

සිංLingua Library has the capability to facilitate the conversion of Sinhala audio into text transcripts. This utilizes the `sinhala_audio` package to perform audio-to-text conversion and provides a simple interface for users to transcribe Sinhala audio files.

## Usage

The library provides two methods to convert Sinhala audio into text: one using a file path and another by taking user input for the audio file. Here's how you can use them:

### Method 1: Conversion from File Path. 

The library provides a function named `conversion()` to convert Sinhala audio into text. Here's how you can use it:

```python
from sinhala_data_processor.sinhala_audio.audio_to_text import conversion

audio_path = "path/to/audio/file.wav"
transcript = conversion(path=audio_path)
print(transcript)
```

### Method 2: Conversion by User Input. 

The library provides a function named `conversion_by_input()` to convert Sinhala audio into text. Here's how you can use it:

```python
from sinhala_data_processor.sinhala_audio.audio_to_text import conversion_by_input

transcript = conversion_by_input()
print(transcript)
```



## Examples

Here's an example of how you can use the library to convert a Sinhala audio file to text using both methods:

```python
from sinhala_data_processor.sinhala_audio.audio_to_text import conversion, conversion_by_input

# Method 1: Conversion from file path

audio_path = "path/to/audio/file.wav"
transcript = conversion(path=audio_path)
print(transcript)

# Method 2: Conversion by user input

transcript = conversion_by_input()
print(transcript)
```
both the `conversion()` function and the `conversion_by_input()` function, demonstrating two different ways users can convert Sinhala audio into text transcripts using සිංLingua library. 

## Predict the Most Suitable word using Machine Learning and Mapping the Grammar Rules.
[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/1.%20Singlish%20to%20Sinhala%20Text%20Conversion/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/3.%20Sinhala%20Grammar%20Conversion/README.md)

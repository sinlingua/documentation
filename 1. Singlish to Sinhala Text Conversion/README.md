[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/5.%20Sinhala%20Text%20Summarization/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/2.%20Sinhala%20Audio%20to%20Text%20Conversion/README.md)

# Singlish to Sinhala Text Conversion

The Singlish to Sinhala text conversion component of සිංLingua offers multiple approaches to translate Singlish text to Sinhala. These approaches are designed to suit different requirements and accuracy levels.

`Usual tools` "oyata den kohomada" -> ඔයට ඩෙන් කොහොමඩ

`සිංLingua library` "oyata den kohomada" -> ඔයාට දැන් කොහොමද (oyaata dhaen kohomadha)

## Table of Contents
- [Singlish to Sinhala Text Conversion](#singlish-to-sinhala-text-conversion)
  - [1. Rule-Based Translation](#1-rule-based-translation)
  - [2. Machine Translation using FastText Model](#2-machine-translation-using-fasttext-model)
  - [3. Hybrid Translation](#3-hybrid-translation)
    - [3.1. Machine Mask Translation](#31-machine-mask-translation)
    - [3.2. Machine Suggest Translation](#32-machine-suggest-translation)
      - [3.2.1. Approach 1](#321-approach-1)
      - [3.2.2. Approach 2](#322-approach-2)
    - [Optional Parameters](#optional-parameters)
  - [4. Manual Translation](#4-manual-translation)
    - [1. Generate Coordinates](#1-generate-coordinates)
    - [2. Replace Cells](#2-replace-cells)
    - [3. Manual Masking](#3-manual-masking)
    - [4. Reconstruct Text](#4-reconstruct-text)
- [Getting Started](#getting-started)
- [Note](#note)

## 1. Rule-Based Translation

The **Rule-Based Translation** approach involves converting Singlish text to Sinhala using a predefined set of rules. This method is efficient and provides quick translations based on specific patterns. To use this approach, the library provides a class `RuleBasedTransliterator`, which can be used as follows:

```python
from sinlingua.singlish.rulebased_transliterator import RuleBasedTransliterator

transliterator = RuleBasedTransliterator()

singlish_text = "YOUR_SINGLISH_TEXT"
sinhala_text = transliterator.transliterator(singlish_text)
print(sinhala_text)
```

## 2. Machine Translation using FastText Model

The **Machine Translation** approach using the FastText model involves leveraging word embeddings to enhance translation accuracy. This method uses FastText's pre-trained Sinhala word vectors to identify similar words for each word in the translated text. The process is as follows:

1. Convert Singlish text to Sinhala using the Rule-Based Translation approach.
2. Utilize the FastText Sinhala word vectors to find similar words for each translated word.
3. Enhance the translated text by replacing each word with its corresponding similar word from the FastText model.

 To use this approach, the library provides a class `MachineTransliterator`. Here's how to use the MachineTransliterator with the FastText model:

```python
from sinlingua.singlish.machine_transliterator import MachineTransliterator

# initialize the Machine Transliterator with the FastText model
fasttext_model_path = "path/to/model/cc.si.300.vec"
transliterator = MachineTransliterator(model=fasttext_model_path)

# provide Singlish text as input
singlish_text = "YOUR_SINGLISH_TEXT"

# translate using the Machine Transliterator with FastText
translated_text = transliterator.transliterator(text=singlish_text)
print(translated_text)
```

FastText model can be downloaded by using the given url:
[FastText Model](https://dl.fbaipublicfiles.com/fasttext/vectors-crawl/cc.si.300.bin.gz)

## 3. Hybrid Translation

The **Hybrid Translation** approach combines the rule-based and machine translation methods to provide accurate and context-aware translations. This approach offers a balance between efficiency and accuracy. The `HybridTransliterator` class is also used for this approach:

```python
from sinlingua.singlish.hybrid_transliterator import HybridTransliterator

transliterator = HybridTransliterator(api_key="YOUR_OPENAI_API_KEY", org_key="YOUR_ORGANIZATION_KEY")

singlish_text = "YOUR_SINGLISH_TEXT"
sinhala_text = transliterator.transliterator(text=singlish_text)
print(sinhala_text)
```
### 3.1. Machine Mask Translation
This function enhances machine-translated text by masking misspelled Sinhala words. It identifies misspelled Sinhala words and replaces them with a mask `"<mask>"` to improve text flow.

```python
from sinlingua.singlish.hybrid_transliterator import HybridTransliterator

hybrid = HybridTransliterator(api_key="YOUR_OPENAI_API_KEY", org_key="YOUR_ORGANIZATION_KEY")

rule_text = "YOUR_SINGLISH_TEXT"
masked_text = hybrid.machine_mask(text=rule_text)
print(masked_text)
```

### 3.2. Machine Suggest Translation
This function further refines machine-translated text by suggesting alternative words for masked words. It can be used in two different approaches through the library.

#### 3.2.1. Approach 1
```python
from sinlingua.singlish.rulebased_transliterator import RuleBasedTransliterator
from sinlingua.singlish.hybrid_transliterator import HybridTransliterator
from sinlingua.singlish.manual_transliterator import ManualTransliterator

rulebased = RuleBasedTransliterator()
hybrid = HybridTransliterator(api_key="YOUR_OPENAI_API_KEY", org_key="YOUR_ORGANIZATION_KEY")
manual = ManualTransliterator()

# using manual_mask with generated coordinates
rule_text = "YOUR_SINGLISH_TEXT"
rule_based_output = rulebased.transliterator(text=rule_text)
coordinates_df = manual.generate_coordinates(text=rule_based_output)
# coordinates of words to be masked can be found by printing coordinates_df.
# ex: [(row, column), (row, column)]
coordinates_list = [(0, 0), (0, 2)]
masked_text, changes = manual.manual_mask(dataframe=coordinates_df, coordinates=coordinates_list)
suggested_text = hybrid.machine_suggest(text=masked_text, changes=changes)
print(suggested_text)
```

#### 3.2.2. Approach 2
```python
from sinlingua.singlish.rulebased_transliterator import RuleBasedTransliterator
from sinlingua.singlish.hybrid_transliterator import HybridTransliterator
from sinlingua.singlish.manual_transliterator import ManualTransliterator

rulebased = RuleBasedTransliterator()
hybrid = HybridTransliterator(api_key="YOUR_OPENAI_API_KEY", org_key="YOUR_ORGANIZATION_KEY")
manual = ManualTransliterator()

# using machine_mask with generated coordinates
rule_text = "YOUR_SINGLISH_TEXT"
masked_text = hybrid.machine_mask(text=rule_text)
coordinates_df = manual.generate_coordinates(text=masked_text)
# coordinates of masked words can be found by printing coordinates_df.
# ex: [(row, column), (row, column)]
coordinates_list = [(0, 0), (0, 2)]
masked_text, changes = manual.manual_mask(dataframe=coordinates_df, coordinates=coordinates_list)
suggested_text = hybrid.machine_suggest(text=masked_text, changes=changes)
print(suggested_text)
```

### Optional Parameters
1. `prompt_masking: str` For change masking prompt from the default prompt
2. `prompt_suggestion: str` For change word suggesting prompt from the default prompt

#### To view the default prompts:
```python
from sinlingua.singlish.hybrid_transliterator import HybridTransliterator

hybrid = HybridTransliterator()

# level van be 0 or 1 for masking prompt and word suggesting prompt respectively
level = 0
hybrid.view_prompt(level=level)
```

Sure, here is the section for the Manual Translation component, including the steps you provided:


## 4. Manual Translation

The **Manual Translation** approach allows you to manually manipulate and modify translations according to your preferences. This can be useful for refining translations and making context-specific adjustments. The `ManualTransliterator` class provides various methods to aid in this process.

### 1. Generate Coordinates

The first step in manual translation is generating coordinates for each word in the Sinhala text. Coordinates uniquely identify each word and its position in the text. This can be done using the `generate_coordinates` method. 

```python
from sinlingua.singlish.manual_transliterator import ManualTransliterator

manual = ManualTransliterator()
sinhala_text = "YOUR_SINHALA_TEXT"
df = manual.generate_coordinates(text=sinhala_text, max_columns=20)
print(df)
```

To visualize the coordinates, you can export them to a CSV file using the `to_csv` method.

```python
manual.to_csv(dataframe=df, file="dataframe.csv")
```

### Optional parameters
1.  `max_columns: int` You can specify the maximum number of columns in the coordinate plane.

### 2. Replace Cells

This method allows you to manually replace specific cells in the coordinate plane with desired words. You need to generate coordinates using the `generate_coordinates` method. Then, create a replacement dictionary where keys are the coordinates to be replaced and values are the replacement words. The `replace_cells` method returns a new dataframe with the changes applied.

```python
from sinlingua.singlish.manual_transliterator import ManualTransliterator

manual = ManualTransliterator()
sinhala_text = "MISSPELLED_SINHALA_TEXT"
df = manual.generate_coordinates(text=sinhala_text)
print(df)

replacement_dictionary = {
    (0, 1): "WORD_TO_BE_REPLACED", # (0, 1) is a coordinate which represents row 0, column 1
    (0, 7): "WORD_TO_BE_REPLACED" # (0, 7) is a coordinate which represents row 0, column 7
}

changed_df, track_changes = manual.replace_cells(dataframe=df, replacement_dict=replacement_dictionary)
print(changed_df)

```

 You can also use the `undo_changes` method to revert the changes if needed.

```python
original_df = manual.undo_changes(dataframe=changed_df, changes=track_changes)
print(original_df)
```

### 3. Manual Masking

Manual masking involves masking specific words in the coordinate plane to be replaced later. Similar to the previous steps, you generate coordinates using the `generate_coordinates` method. Specify the coordinates you want to mask, and then use the `manual_mask` method. The resulting `reconstructed_text` can be passed to the `machine_suggest` method from the Hybrid Translation approach to find the best-matching words for the masked positions.

```python
from sinlingua.singlish.manual_transliterator import ManualTransliterator

manual = ManualTransliterator()
sinhala_text = "MISSPELLED_SINHALA_TEXT"
df = manual.generate_coordinates(text=sinhala_text)
print(df)

coordinates = [(0, 1), (0, 7)]  # Example coordinates to mask
reconstructed_text, changes = manual.manual_mask(dataframe=df, coordinates=coordinates)
print(reconstructed_text)

# You can use machine_suggest to find matches for masked words
```

### 4. Reconstruct Text

Finally, the `reconstruct_text` method allows you to convert the modified dataframe back into a text. This step completes the manual translation process.

```python
from sinlingua.singlish.manual_transliterator import ManualTransliterator

manual = ManualTransliterator()
sinhala_text = "YOUR_SINHALA_TEXT"
df = manual.generate_coordinates(text=sinhala_text)
print(df)

constructed_text = manual.reconstruct_text(dataframe=df)
print(constructed_text)
```

These manual translation methods provide flexibility and control over the translation process, enabling you to refine translations based on specific requirements.

---
For usage examples and detailed documentation, visit the [සිංLingua GitHub repository](https://github.com/SupunGurusinghe/SinlinguaDocumentation/).


Please remember to replace `"YOUR_SINHALA_TEXT"` and `"MISSPELLED_SINHALA_TEXT"` with the actual Sinhala text you are working with. Also, replace `"YOUR_USERNAME/REPO"` with your actual GitHub repository information.

## Getting Started

To use the Singlish to Sinhala text conversion component of සිංLingua, follow these steps:

1. Install the සිංLingua library:
   ```bash
   pip install sinlingua
   ```

2. Import the required classes for the chosen translation approach:
   ```python
   from sinlingua.singlish.rulebased_transliterator import RuleBasedTransliterator
   from sinlingua.singlish.machine_transliterator import MachineTransliterator
   from sinlingua.singlish.hybrid_transliterator import HybridTransliterator
   from sinlingua.singlish.manual_transliterator import ManualTransliterator
   ```

3. Initialize the transliterator class based on your chosen approach:
   ```python
   rulebased = RuleBasedTransliterator()  # For Rule-Based Translation 
   machine = MachineTransliterator()  # For Machine Translation   
   hybrid = HybridTransliterator(api_key="YOUR_OPENAI_API_KEY", org_key="YOUR_ORGANIZATION_KEY")  # For Hybrid Translation
   manual = ManualTransliterator()  # For Manual Translation
   ```

4. Use the functions of the above mentioned classes accordingly

# Note

- Make sure to replace `"YOUR_OPENAI_API_KEY"` and `"YOUR_ORGANIZATION_KEY"` with your actual OpenAI API key and organization key.

[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/5.%20Sinhala%20Text%20Summarization/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/2.%20Sinhala%20Audio%20to%20Text%20Conversion/README.md)


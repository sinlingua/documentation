[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/2.%20Sinhala%20Audio%20to%20Text%20Conversion/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/4.%20Sinhala%20Text%20Preprocessing/README.md)

# Sinhala Grammatical Rule Mapping

The examples below demonstrates the usage of the `GrammarMain` class to correct an informal Sinhala sentence into a formal one.

## Usage

If a sentence starts with "මම" or "මා" in present tense, it should end with "මි".

## Example

Consider the following code segment:

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "මා සතුන්ට දානයක් දෙන්න හිතන් ඉන්නවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
මම සතුන්ට දානයක් දෙන්න හිතන් ඉන්නෙමි
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "මා සතුන්ට දානයක් දෙන්න හිතන් ඉන්වා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
මම සතුන්ට දානයක් දෙන්න හිතන් ඉන්නෙමි
```
## Usage

If a sentence starts with "අප" or "අපි" in present tense, it should end with "මු".

## Examples

Consider the following code segment:

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "අපි පොසොන් පෝයට දන්සලක් සංවිධානය කරනවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
අපි පොසොන් පෝයට දන්සලක් සංවිධානය කරමු
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "අපි පොසොන් පෝයට දන්සලක් සංවිධානය කරවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
අපි පොසොන් පෝයට දන්සලක් සංවිධානය කරමු
```

## Usage

If a sentence starts with "මම" or "මා" in future tense, it should end with "න්නෙමි" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "මම මේ ටික හොඳට බලන් කියලා දෙන්නම්"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
මම මේ ටික හොඳට බලන් කියලා දෙන්නෙමි
```

## Usage

If a sentence starts with "අප" or "අපි" in future tense, it should end with "න්නෙමු" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "අප හෙට මේ වෙලාවට නිදාගෙන හිඳීවි"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
අපි හෙට මේ වෙලාවට නිදාගෙන හිඳන්නෙමු
```

## Usage

If a sentence starts with "මම" or "මා" in past tense, it should end with "ෙමි" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "මා කෝප්පෙන් වතුර බිව්වා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
මම කෝප්පෙන් වතුර බිව්වෙමි
```

## Usage

If a sentence starts with "අප" or "අපි" in past tense, it should end with "ෙමු" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "අපි කෑම කෑවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
අපි කෑම කෑවෙමු
```

## Usage

If a sentence starts with "ඇය" or "ඈ" in present tense, it should end with "යි" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඇය පිටිසර පාසලක උත්සහයෙන් උගන්වනවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඇය පිටිසර පාසලක උත්සහයෙන් උගන්වයි
```

## Usage

If a sentence starts with "ඇය" or "ඈ" in past tense, it should end with "ය" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඇය මල් නෙලුවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඇය මල් නෙලුවාය
```

## Usage

If a sentence starts with "ඔහු" in present tense, it should end with "යි" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔහු ඉතා ආදරයෙන් දෙමාපියන් නමදිනවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔහු ඉතා ආදරයෙන් දෙමාපියන් නමදියි
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔහු ඉතා ආදරයෙන් දෙමාපියන් නමදිනව"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔහු ඉතා ආදරයෙන් දෙමාපියන් නමදියි
```

## Usage

If a sentence starts with "ඔහු" in past tense, it should end with "ේය" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔහු මල් නෙලුවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔහු මල් නෙලුවේය
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔහු මල් නෙලුව"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔහු මල් නෙලුවේය
```

## Usage

If a sentence starts with "ඔවුන්" or "ඔවුහු" in present tense, it should end with "ති" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔවුන් නොයෙක් ආකාරයේ ඇඳුම් මහනවාලු"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔවුන් නොයෙක් ආකාරයේ ඇඳුම් මහති
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔවුන් නොයෙක් ආකාරයේ ඇඳුම් මහනව"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔවුන් නොයෙක් ආකාරයේ ඇඳුම් මහති
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔවුහු නොයෙක් ආකාරයේ ඇඳුම් මහනව"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔවුහු නොයෙක් ආකාරයේ ඇඳුම් මහති
```

## Usage

If a sentence starts with "ඔවුන්" or "ඔවුහු" in past tense, it should end with "ෝය" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔවුන් හවස් වී ගෙදර ගියා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔවුන් හවස් වී ගෙදර ගියෝය
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ඔවුහු හවස් වී ගෙදර ගියා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ඔවුහු හවස් වී ගෙදර ගියෝය
```

## Usage

If a sentence starts with "තී" or "තෝ" or "ඔබ" or "නුඹ" in past tense, it should end with "ෙහි" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "තී මල් කැඩුවද"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
තී මල් කැඩුවෙහි
```

## Usage

If a sentence starts with "තෙපි" or "තොපි" in past tense, it should end with "ෙහු" according to the tense and verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "තොපි ආහාර ලෑස්ති කරාද"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
තොපි ආහාර ලෑස්ති කරෙහු
```

## Usage

If a sentence starts with a plural subject in present tense, it should end with a plural verb in present tense.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ගොවියෝ මහන්සි වී රටට සහල් සපයනවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ගොවියෝ මහන්සි වී රටට සහල් සපයති
```

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ගොවියෝ මහන්සි වී රටට සහල් සපයන"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ගොවියෝ මහන්සි වී රටට සහල් සපයති
```

## Usage

If a sentence starts with a plural subject in past tense, it should end with a plural verb in past tense.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "ගුරුවරු පිටතට පැමිණ සිටියා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
ගුරුවරු පිටතට පැමිණ සිටියෝය
```

## Usage

If a sentence starts with a singular subject in present tense, it should end with a singular verb.

## Examples

```python
from sinhala_data_processor.grammar_rule.grammar_main import GrammarMain

# Create an instance of GrammarMain
obj = GrammarMain()

# Original informal sentence
sentence = "දරුවා වෙහෙස මහන්සියෙන් ඉගෙන ගන්නවා"

# Apply grammar correction
corrected_sentence = obj.mapper(sentence=sentence)
print(corrected_sentence)
```

Output:

```
දරුවා වෙහෙස මහන්සියෙන් ඉගෙන ගනියි
```


[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/2.%20Sinhala%20Audio%20to%20Text%20Conversion/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/4.%20Sinhala%20Text%20Preprocessing/README.md)

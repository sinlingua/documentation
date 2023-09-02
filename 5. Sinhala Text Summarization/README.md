[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/4.%20Sinhala%20Text%20Preprocessing/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/1.%20Singlish%20to%20Sinhala%20Text%20Conversion/README.md)

# Sinhala Text Summarization & Translation

The Sinhala Text Summarization & Translation component of සිංLingua offers multiple approaches to translate Sinhala Text Summarization & Translation. These approaches are designed to suit different requirements and accuracy levels.This project focuses on leveraging state-of-the-art Natural Language Processing (NLP) models to summarize Sinhala text. Various techniques and models have been explored to provide optimal, efficient, and accurate summaries.

`Usual tools` have not customizing sinhala text summarization & translation capabilites.

`සිංLingua library` has given more accurate and enhanced customizing sinhala text summarization & translation capabilities.


## Table of Contents
- [Sinhala Text Summarization & Translation](#sinhla-text-summarization-&-translation)
  - [1. TF-IDF Summarizer](#1-tf-idf-summarizer)
    - [1.1. Summarized By Precentage](#11-summarized-by-percentage)
    - [1.2. Summarized By Word Count Limit](#12-summarized-by-word-count-limit)
    - [1.3. Language Translation](#13-language-translation)
  - [2. Bert Summarizer](#2-bert-summarizer-model)
    - [2.1. Summarized By Precentage](#21-summarized-by-percentage)
    - [2.2. Summarized By Word Count Limit](#22-summarized-by-word-count-limit)
    - [2.3. Language Translation](#23-language-translation)
  - [3. Longformer Summarizer](#3-longformer-summarizer-model)
    - [3.1. Summarized By Precentage](#31-summarized-by-percentage)
    - [3.2. Summarized By Word Count Limit](#32-summarized-by-word-count-limit)
    - [3.3. Language Translation](#33-language-translation)
  - [4. Faster Bert Summarizer](#4-faster-bert-summarizer-model)
    - [4.1. Summarized By Precentage](#41-summarized-by-percentage)
    - [4.2. Summarized By Word Count Limit](#42-summarized-by-word-count-limit)
    - [4.3. Language Translation](#43-language-translation)
  - [5. Faster Longformer Summarizer](#5-faster-longformer-summarizer-model)
    - [5.1. Summarized By Word Count Limit](#51-summarized-by-word-count-limit)
    - [5.2. Language Translation](#52-language-translation)
- [Getting Started](#getting-started)
- [Note](#note)


## 1. TF-IDF Summarizer

A traditional method for text summarization.Uses the Term Frequency-Inverse Document Frequency algorithm to evaluate the importance of sentences.
Suitable for shorter texts where context and semantic understanding may not be as crucial.To use this approach, the library provides a class `TFIDFTextSummarizer`, which can be used as follows:

### 1.1. Summarized By Percentage

To summarize by a certain percentage of the original text:

```python
from sinlingua.summarizer.tf_idf import TFIDFTextSummarizer
text_summarizer = TFIDFTextSummarizer()
sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

summary = text_summarizer.summarize_by_percent(sample_text, percent=50)
print(summary)
```

### 1.2. Summarized By Word Count Limit

To summarize by a specific word count:

```python
 from sinlingua.summarizer.tf_idf import TFIDFTextSummarizer
 text_summarizer = TFIDFTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PHARAGRAPH"

 summary = text_summarizer.summarize_by_word_count(sample_text, word_count=400)
 print(summary)
```

### 1.3. Language Translation

To translate the Sinhala summary into English:

```python
 from sinlingua.summarizer.tf_idf import TFIDFTextSummarizer
 text_summarizer = TFIDFTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summarized_text = text_summarizer.summarize_by_percent(sample_text, percent=40)
 translated_text = text_summarizer.translate_to_english(summarized_text)
 print(translated_text)
```

## 2. Bert Summarizer

BERT (Bidirectional Encoder Representations from Transformers) is a cutting-edge transformer-based model known for its effectiveness in NLP tasks.
This component utilizes BERT's capabilities to understand the contextual relationship between words in Sinhala text and generate relevant summaries.
Ideal for longer texts where context is essential.To use this approach, the library provides a class `BertTextSummarizer`.

### 2.1. Summarized By Percentage

To summarize by a certain percentage of the original text:
```python
 from sinlingua.summarizer.bert import BertTextSummarizer
 text_summarizer = BertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"
 summary = text_summarizer.summarize_by_percent(sample_text, percent=50)
 print(summary))
```

### 2.2. Summarized By Word Count Limit

To summarize by a specific word count:

```python
 from sinlingua.summarizer.bert import BertTextSummarizer
 text_summarizer = BertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summary = text_summarizer.summarize_by_word_count(sample_text, word_count=30)
 print(summary)
```

### 2.3. Language Translation

To translate the Sinhala summary into English:

```python
 from sinlingua.summarizer.bert import BertTextSummarizer
 text_summarizer = BertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summarized_text = text_summarizer.summarize_by_percent(sample_text, percent=20)
 translated_text = text_summarizer.translate_to_english(summarized_text)
 print(translated_text)
```

## 3. Longformer Summarizer

Longformer is an extended version of the BERT model designed specifically for longer documents.This component employs Longformer's attention mechanism to generate summaries that capture the essence of extensive Sinhala texts.Solved the issues of Bert Model Limitations.To use this approach, the library provides a class `LongformerTextSummarizer`.

### 3.1. Summarized By Percentage

To summarize by a certain percentage of the original text:
```python
 from sinlingua.summarizer.longformer import LongformerTextSummarizer
 text_summarizer = LongformerTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"
 summary = text_summarizer.summarize_by_percent(sample_text, percent=30)
 print(summary))
```

### 3.2. Summarized By Word Count Limit

To summarize by a specific word count:

```python
 from sinlingua.summarizer.longformer import LongformerTextSummarizer
 text_summarizer = LongformerTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summary = text_summarizer.summarize_by_word_count(sample_text, word_count=30)
 print(summary)
```

### 3.3. Language Translation

To translate the Sinhala summary into English:

```python
 from sinlingua.summarizer.longformer import LongformerTextSummarizer
 text_summarizer = LongformerTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summarized_text = text_summarizer.summarize_by_word_count(sample_text, word_count=400)
 translated_text = text_summarizer.translate_to_english(summarized_text)
 print(translated_text)
```

## 4. Faster Bert Summarizer

An optimized version of the BERT summarizer.Strives to maintain the balance between speed and summary quality.Uses techniques like sentence embeddings and cosine similarity to reduce the processing time while keeping the context intact.To use this approach, the library provides a class `FBertTextSummarizer`.


### 4.1. Summarized By Percentage

To summarize by a certain percentage of the original text:
```python
 from sinlingua.summarizer.faster_bert import FBertTextSummarizer
 text_summarizer = FBertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"
 summary = text_summarizer.summarize_by_percent(sample_text, percent=30)
 print(summary))
```

### 4.2. Summarized By Word Count Limit

To summarize by a specific word count:

```python
 from sinlingua.summarizer.faster_bert import FBertTextSummarizer
 text_summarizer = FBertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summary = text_summarizer.summarize_by_word_count(sample_text, word_count=400)
 print(summary)
```

### 4.3. Language Translation

To translate the Sinhala summary into English:

```python
 from sinlingua.summarizer.faster_bert import FBertTextSummarizer
 text_summarizer = FBertTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 summarized_text = text_summarizer.summarize_by_word_count(sample_text, word_count=400)
 translated_text = text_summarizer.translate_to_english(summarized_text)
 print(translated_text)
```

## 5. Faster Longformer Summarizer

A more efficient variant of the Longformer summarizer.Incorporates techniques to speed up the summarization process without compromising too much on the accuracy and context.To use this approach, the library provides a class `FLongformerTextSummarizer`.


### 5.1. Summarized By Word Count Limit

To summarize by a specific word count:

```python
 from sinlingua.summarizer.faster_longformer import FLongformerTextSummarizer
 text_summarizer = FLongformerTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 refined_summary = text_summarizer.refined_summarize_by_word_count(sample_text, distilbert_word_limit=800, longformer_word_limit=400)
 print("Refined Summary:", refined_summary)
```

### 5.2. Language Translation

To translate the Sinhala summary into English:

```python
 from sinlingua.summarizer.faster_longformer import FLongformerTextSummarizer
 text_summarizer = FLongformerTextSummarizer()
 sample_text = "YOUR_SINHALA_TEXT_PARAGRAPH"

 refined_summary = text_summarizer.refined_summarize_by_word_count(sample_text, distilbert_word_limit=800, longformer_word_limit=400)
 translated_text = text_summarizer.translate_to_english( refined_summary)
 print(translated_text)
```


## Getting Started

To use the Sinhala Text Summarization & Translation component of සිංLingua, follow these steps:

1. Install the සිංLingua library:
   ```bash
   pip install sinlingua
   ```

2. Import the required classes for the chosen translation approach:
   ```python
   
   from sinlingua.summarizer.tf_idf import TFIDFTextSummarizer   
   from sinlingua.summarizer.bert import BertTextSummarizer
   from sinlingua.summarizer.longformer import LongformerTextSummarizer
   from sinlingua.summarizer.faster_bert import FBertTextSummarizer
   from sinlingua.summarizer.faster_longformer import FLongformerTextSummarizer
   
   ```

3. Initialize the summarizer class based on your chosen approach:
   
   ```python
   
   text_summarizer = TFIDFTextSummarizer()  # For tf-idf text summarizer
   text_summarizer = BertTextSummarizer()  # For bert embedding text summarizer
   text_summarizer = LongformerTextSummarizer() # For longformer embedding text summarizer
   text_summarizer = FBertTextSummarizer() # For fast bert embedding text summarizer
   text_summarizer = FLongformerTextSummarizer()  # For fast longformer embedding text summarizer
   
   ```

4. Use the functions of the above mentioned classes accordingly


# Note

- BERT Limit: Remember that the BERT model has a maximum token limit (512 tokens for bert-base-multilingual-uncased). Extremely lengthy sentences or 
  paragraphs may be truncated, which might affect the quality of the embeddings and, thus, the summary.
- Tips:
  For lengthy texts, consider breaking them down into smaller chunks or paragraphs and processing them separately.
- longformer summarization model address the issue of bert summarization limitations.
- mostly recomond longformer, faster longformer version,TF-IDF version for the long document summarization.

--------------------------------------------------------------------------------------------------------------------------------------------------------------
# Example Usage

`Sample Text` """විදුලි බිල හා ජල බිල තුන් හතර ගුණයකින් වැඩිවී, වැඩි කලක් යන්නට මත්තෙන් නැවත විදුලි අර්බුදයක හා ජල අර්බුදයක බර ජනතාවගේ හිස මත කඩා වැටී ඇත. මේ ඊයේ පෙරේදා දෙවනවරටත් ජල ගාස්තු සියයට 50 කට වැඩි ගණනකින් වැඩිකර ඇත. එසේම, නුදුරු අනාගතයේම විදුලි කප්පාදුවකට රජය අර අඳින බව පෙනෙන්නට තිබේ. අමාත්‍ය කංචන විජේසේකරගේ කතා බහෙන්ද ඒ බව ඉඟි කෙරේ. මීට හේතුව රටට බලපා ඇති දැඩි නියං තත්ත්වයයි. මේ නිසා ජල සහ විදුලි කප්පාදුවක් ළඟ ළඟම එන බව අප සියල්ලෝම තේරුම් ගත යුතුව ඇත. ජල සම්පාදන මණ්ඩලය ජලය කපා නොදමනවා කිව්වත් ඇත්ත නම්, පවතින නියඟය තව තව උග්‍ර වුවහොත්, ජල සම්පාදන හා පිරිපහදු මධ්‍යස්ථානවලට පානීය ජලය ලබාගැනීමේ දැඩි ගැටලුවකට මුහුණ දෙන්නට සිදුවීමයි. මෙනිසා ජලය, විදුලිය දැන් සිටම අරපිරිමැස්මෙන් භාවිත කිරීම අප කාගේත් යුතුකම වන අතර, උඩවලවේ අර්බුදය මෙන් විදුලි හා කෘෂිකර්ම ඇමැතිවරු කා කොටා නොගෙන පවතින ජලය කළමනාකරණය කර ගැනීම රජයේ වගකීම ය.

සැබැවින්ම පවතින තත්ත්වයට හේතුව පවතින අයහපත් කාලගුණය බව අප කවුරුත් තේරුම් ගත යුතුය. නමුත් මේ කාලගුණ අනාවැකිය කලින් නොකී බවට කාලගුණ දෙපාර්තමේන්තුවට ද චෝදනා එල්ලවී ඇත. පවතින අයහපත් වියළි කාලගුණික තත්ත්වය අප රටට පමණක් බලපා ඇති එකක් නොවන බව ගෝලීය තත්ත්වය විමර්ශනය කිරීමේදී පැහැදිලි වන කාරණයකි. මෙවර දැඩි ගිනියම යුරෝපයට කළින්ම බලපෑවේය. මීට මාසයකට එක හමාරකට පෙර සිටම ඉතාලිය, ජර්මනිය, කැනඩාව, ප්‍රංශය ඇතුළු යුරෝපාකරය දැවෙන්නට වූ අතර එහි උෂ්ණත්වය සෙන්ටිග්‍රේඩ් අංශක 42 ඉක්මවූ අවස්ථා ද වාර්තා විය. මෙහි ඊළඟ බලපෑම ධ්‍රැව ප්‍රදේශවල (ආර්ක්ටික් සහ ඇන්ටාර්ක්ටික්) හිම කඳු දියවී මුහුදු මට්ටම ඉහළ යෑමයි. එහි බලපෑම මුහුදු මට්ටම ඉහළ ගොස්, පහත් බිම් යටවීම හා ගංගා දිගේ කරදිය ඉහළට ගලා යෑමයි. ඒ මගින් ද නැවත පානීය ජල අර්බුදයක් නිර්මාණය වේ. නොහොත් ජල අර්බුදය උග්‍ර වේ.

ශාන්තිකර සාගරය රත්වීමෙන් උණුසුම් වාත දහරා ලෝකය පුරා සංසරණය වීම නොහොත් වසර කිහිපයකට වරක් සිදුවන “එල්නිනෝ” සංසිද්ධිය ලෝකයේ මේ දිනවල පවතින මෙම වියළි තත්ත්වයට හේතුව බව කාලගුණ විද්‍යාඥයෝ පවසති. එබැවින් සොබාදහමේ මේ රීතීන්ට යටත්ව අපගේ කටයුතු කරගෙන යෑමට සිදුව ඇත. එනිසා නියඟයක් ආ පමණින් ආණ්ඩුවටම බැණ අඬගැසීමෙන් ඵලක් නැත. ඒ සඳහා පෙර සූදානම අප කා තුළත් පුරුදු පුහුණු කර තිබිය යුතුය. එම පෙර පුහුණුව සඳහා කාලගුණයෙන් හෝ ආපදා කළමනාකරණයෙන් අපට සූදානමක් ලබානොදීම වෙනම කතාවකි. එසේ පෙර සූදානමක් රජයට තිබුණා නම් උඩවලව ව්‍යාපාරයේ ගොවීන් කුලප්පු වන්නට කළින් යහපත් ලෙස එම අර්බුදය කළමනාකරණය කරන්නට රජයට හැකිව තිබිණි. නමුත්, කෘෂිකර්ම ඇමැති එක පැත්තක, විදුලි බල ඇමැති එක පැත්තක, වාරිමාර්ග ඇමැති එක පැත්තක යන සාමූහික නොවන ගමනක් තවම යන ආණ්ඩු ක්‍රමවේදයක රට පවතින බව අපට ඉතා හොඳින් පැහැදිලිය.

රටේ ප්‍රධාන ගංගා 103 ක් හා වැව් 35,000 ක් තිබුණද මාස දෙකක් රටට වැසි නොවැටුණොත් ජලය නැති රටක් බවට රට මේ වන විට පත්වීම මහා අර්බුදයකි. එක ජලාශයක් පවතින ඊශ්‍රායලය හා මෙතරම් ගංගා, දිය කඳුරු, වැව්, පොකුණු ඇති රටක සෞභාග්‍යය ගැන අපට කියන්නට ඇත්තේ දුකම දුක හිතෙන කතාවකි. ඒ තරමටම මැති සබේ 225 ක නියෝජනය රටට හොඳටම කර ඇත.

මේ වන විට සහල්, එළවළු, බිත්තර, මස්, මාළු යනාදී අත්‍යවශ්‍ය ආහාර සියල්ලේම මිල ගණන් කොතරම් ඉහළ ද යන්න අපි සැවොම දන්නා කාරණයකි. මේ සියල්ලටම තාමත් දමන ගැලවිජ්ජාව ඩොලර් අර්බුදය ය. නමුත්, රට යම් තාක් දුරට යථා තත්ත්වයකට පත්ව ඇති බව පෙනෙන්නට තිබේ. නමුත් අත්‍යවශ්‍ය ආහාර ද්‍රව්‍යවල මිල ඉහළ ගොස් තිබීම හා එළවළු, මස්, මාළු ටික පවා පිටරටින් ගෙන එන්නට ක්‍රියාකිරීම ජලය, විදුලිය ඇතුළු රටේ සම්පත් නිසි ලෙස කළමනාකරණය නොකරන බවට කදිම සාධකයකි,

මේ වන විට බොහෝ ජනයා ජීවත්වීම සඳහා අපමණ දුකක් විඳිති. ඇතැමුන්ට රැකියා අහිමිව ඇත. බොහෝ කම්හල් සේවකයින්ගේ සේවා කාලය හාම්පුතුන් විසින් සීමා කර ඇත. ඇතැම් ප්‍රකට ගාමන්ට් ෆැක්ටරිවල පවා තම සේවකයින්ට මාසයකට වැඩ දෙන්නේ දින 15 ක පමණ කාලයකි. බොහෝ ආයතනවල වාර්ෂික පඩි වැඩිකිරීම්, පාරිතෝෂික දීමනා කිසිවක් ලබාදෙන්නේ නැත. රුපියල් ලක්ෂයක් – දෙකක් පඩි ගත් විධායක ශ්‍රේණිවල, බැංකු සේවකයින්ගේ වැනි අයගෙන් බදු කැපීම නිසා මාසෙකට දෙකකට ඔවුන් හෝටලයකට ගොස් ගත් ෆන් එක පවා නතරකිරීම නිසා රට පුරා දේශීය සංචාරකයින්ගෙන් යැපුණු හෝටල්, අවන්හල් පද්ධතිය ද නැට්ටටම කඩාවැටී ඇත. මෙනිසා ජනතාවගේ ජීවන මාර්ග ඇහිරී, ආදායම් මාර්ග සීමාවී හොඳටම පටි තදකරගන්නට සිදුවී දැන් මාස හත – අටක් ගෙවී ගොස් ඇත. එවන් විටෙක විටින් විට වැඩිවන විදුලි බිල්පත, ජල බිල්පත මහත් කොඩිවිනයක් බවට පත්වෙමින් තිබේ.

මේ සඳහා රජය තිරසාර විසඳුමකට යෑම අවශ්‍ය වන අතර, රටේ ජලය, වනාන්තර ඇතුළු රක්ෂිත ජල පෝෂක භූමි ප්‍රදේශ සංරක්ෂණය සඳහා අවශ්‍ය පියවර අඩු නැතිව ගත යුතුය. නමුත් අපට දකින්නට ඇත්තේ ජල, විදුලි අර්බුද ඇතිවන්නේ නැති තාක්, රටේ ස්වභාවික සම්පත් සංරක්ෂණය සඳහා ඇහැට ඇඟිල්ලෙන් ඇනලා කිව්වත් ගණන් නොගන්නා බලධාරීන් ප්‍රශ්නයක් උග්‍රවූ විට පමණක් රෙදි උනාගෙන කෑමොර දෙන බවක් පමණි. මේ නිසා සැබෑ සිස්ටම් චේන්ජ් එකක් රටට අත්‍යවශ්‍ය ම ය."""

`Summarize By Wordcount(400 words)`"""විදුලි බිල හා ජල බිල තුන් හතර ගුණයකින් වැඩිවී, වැඩි කලක් යන්නට මත්තෙන් නැවත විදුලි අර්බුදයක හා ජල අර්බුදයක බර ජනතාවගේ හිස මත කඩා වැටී ඇත. මේ ඊයේ පෙරේදා දෙවනවරටත් ජල ගාස්තු සියයට 50 කට වැඩි ගණනකින් වැඩිකර ඇත. එසේම, නුදුරු අනාගතයේම විදුලි කප්පාදුවකට රජය අර අඳින බව පෙනෙන්නට තිබේ. මේ නිසා ජල සහ විදුලි කප්පාදුවක් ළඟ ළඟම එන බව අප සියල්ලෝම තේරුම් ගත යුතුව ඇත. සැබැවින්ම පවතින තත්ත්වයට හේතුව පවතින අයහපත් කාලගුණය බව අප කවුරුත් තේරුම් ගත යුතුය. නමුත් මේ කාලගුණ අනාවැකිය කලින් නොකී බවට කාලගුණ දෙපාර්තමේන්තුවට ද චෝදනා එල්ලවී ඇත. පවතින අයහපත් වියළි කාලගුණික තත්ත්වය අප රටට පමණක් බලපා ඇති එකක් නොවන බව ගෝලීය තත්ත්වය විමර්ශනය කිරීමේදී පැහැදිලි වන කාරණයකි. මෙහි ඊළඟ බලපෑම ධ්‍රැව ප්‍රදේශවල (ආර්ක්ටික් සහ ඇන්ටාර්ක්ටික්) හිම කඳු දියවී මුහුදු මට්ටම ඉහළ යෑමයි. එහි බලපෑම මුහුදු මට්ටම ඉහළ ගොස්, පහත් බිම් යටවීම හා ගංගා දිගේ කරදිය ඉහළට ගලා යෑමයි. එබැවින් සොබාදහමේ මේ රීතීන්ට යටත්ව අපගේ කටයුතු කරගෙන යෑමට සිදුව ඇත. ඒ සඳහා පෙර සූදානම අප කා තුළත් පුරුදු පුහුණු කර තිබිය යුතුය. එම පෙර පුහුණුව සඳහා කාලගුණයෙන් හෝ ආපදා කළමනාකරණයෙන් අපට සූදානමක් ලබානොදීම වෙනම කතාවකි. එසේ පෙර සූදානමක් රජයට තිබුණා නම් උඩවලව ව්‍යාපාරයේ ගොවීන් කුලප්පු වන්නට කළින් යහපත් ලෙස එම අර්බුදය කළමනාකරණය කරන්නට රජයට හැකිව තිබිණි. රටේ ප්‍රධාන ගංගා 103 ක් හා වැව් 35,000 ක් තිබුණද මාස දෙකක් රටට වැසි නොවැටුණොත් ජලය නැති රටක් බවට රට මේ වන විට පත්වීම මහා අර්බුදයකි. එක ජලාශයක් පවතින ඊශ්‍රායලය හා මෙතරම් ගංගා, දිය කඳුරු, වැව්, පොකුණු ඇති රටක සෞභාග්‍යය ගැන අපට කියන්නට ඇත්තේ දුකම දුක හිතෙන කතාවකි. මේ වන විට සහල්, එළවළු, බිත්තර, මස්, මාළු යනාදී අත්‍යවශ්‍ය ආහාර සියල්ලේම මිල ගණන් කොතරම් ඉහළ ද යන්න අපි සැවොම දන්නා කාරණයකි. නමුත්, රට යම් තාක් දුරට යථා තත්ත්වයකට පත්ව ඇති බව පෙනෙන්නට තිබේ. බොහෝ කම්හල් සේවකයින්ගේ සේවා කාලය හාම්පුතුන් විසින් සීමා කර ඇත. ඇතැම් ප්‍රකට ගාමන්ට් ෆැක්ටරිවල පවා තම සේවකයින්ට මාසයකට වැඩ දෙන්නේ දින 15 ක පමණ කාලයකි. බොහෝ ආයතනවල වාර්ෂික පඩි වැඩිකිරීම්, පාරිතෝෂික දීමනා කිසිවක් ලබාදෙන්නේ නැත. මෙනිසා ජනතාවගේ ජීවන මාර්ග ඇහිරී, ආදායම් මාර්ග සීමාවී හොඳටම පටි තදකරගන්නට සිදුවී දැන් මාස හත – අටක් ගෙවී ගොස් ඇත. එවන් විටෙක විටින් විට වැඩිවන විදුලි බිල්පත, ජල බිල්පත මහත් කොඩිවිනයක් බවට පත්වෙමින් තිබේ. මේ සඳහා රජය තිරසාර විසඳුමකට යෑම අවශ්‍ය වන අතර, රටේ ජලය, වනාන්තර ඇතුළු රක්ෂිත ජල පෝෂක භූමි ප්‍රදේශ සංරක්ෂණය සඳහා අවශ්‍ය පියවර අඩු නැතිව ගත යුතුය."""

`Translation Feature(English)` """The electricity bill and the water bill increased by three folds, and soon the weight of a power crisis and the weight of the water crisis had collapsed.The water fees have been increased by more than 50 percent yesterday.Also, the government has seen that the government is trying to make a power cut in the near future.Therefore, we all need to understand that we will be nearing water and power cuts.Of course, we all need to understand that the cause of the situation is the cause of bad weather.However, the Department of Meteorology has also been accused of not saying the weather forecast.In the investigation of the global conditions that the existing bad dry weather condition is not a result of our country.The next effect here is the rising hills of the polar-in-polate-country.The impact of its impact goes up the sea level, falling lowlands and flows along the rivers.Therefore, it has been to carry out our work subject to these rules of nature.Prepare for this purpose we must have been trained in.It is a separate story to not prepare for the previous training for the previous training.If the government had prepared preparation, the government was able to manage the crisis in the Udawalawa movement.Although there were 103 major rivers and 35,000 civilians, the country is a great crisis if the country is not waterless.It has been a sad story that is the prosperity of Israel and rivers, wanks, wanks, ponds, ponds, and ponds.We are all knowing how high is the price of rice, vegetables, eggs, meat, fish.But the country seems to be restored to some extent.Most factory employees have been limited by employers.Some of the famous garant factories spend a month for about 15 days.There are no annual stairs, gratuity allowances of many institutions.The seven-eight months have passed since the living roads of the people of the people and the living routes of the people.At times, the increasing electricity bill, the water bill is becoming a huge codow.The government needs to go to a sustainable solution, and should not be reduced to conservation of water,forests."""




[![Previous](https://img.shields.io/badge/previous-green.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/4.%20Sinhala%20Text%20Preprocessing/README.md)
[![Home](https://img.shields.io/badge/home-orange.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/blob/main/README.md)
[![Next](https://img.shields.io/badge/next-blue.svg)](https://github.com/SupunGurusinghe/SinlinguaDocumentation/tree/main/1.%20Singlish%20to%20Sinhala%20Text%20Conversion/README.md)

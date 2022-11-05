## Introduction

Khasi is one of the languages spoken in the Indian state of Meghalaya. There are variations in usage of diacrities depending on the dialects and literature genres.
Language Code: kha(ISO 639-2).

## Need for OCR

khasi has almost similar number of alphabets compared to english. Dictionaries have high occurence of diacritical characters compared to newspapers. Academic textbooks have low to moderate usage of diacritical characters. The usage of latin OCR introduced false positives in case of diacritical characters on dictionary images usually. Hence this is an effort to build an OCR model that recognises characters in all khasi literature genres.

## Source of Training text

training text were taken from [U Nongsain Hima e-newspaper archives](https://www.nongsain.com/archives.aspx). Refer to [preparing-corpus](https://github.com/udaycruise2903/hello_matrix/wiki/preparing-corpus) for preparing training and evaluation text.

## Evaluation Results

eval text is from the same source and hence CER = 0.08% is achieved.

## UNLV test reports

![UNLV-test-reports-image](https://github.com/udaycruise2903/khasi-ocr/blob/kha_fastv1.0/test/langtests/reports/kha-unlv-test%20-%20Sheet1-cropped.png)
[image testsets](https://github.com/udaycruise2903/imgtestsets-kha)

dictionary testset contains pages of high number of diacritical characters.
textbooks testset contains images of 12th Grade textbook which has moderate number of diacrities.
groundtruth of these testsets were generated using latin.trianeddata(best model). Hence accuracy is >97% for best_latin in UNLV tests

In comparision to best_latin model, kha.traineddata(fast model) delivers 95.7% character accuracy. This model can recognise standard khasi in mainstream literature genres

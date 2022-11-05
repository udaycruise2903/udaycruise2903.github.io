## Edit language-specific.sh

include ‘kha’ in VALID_LANGUAGES_CODES
include “Liberation Serif” in in LATIN_FONTS
inserrt kha ) :: under #LATIN with default treatment

## create starter traineddata

use tesstrain.sh to generate starter traineddata using kha.train.training_text and kha.eval.training_text for‘kha’.
If specified -lang option is not available in tessdatadir, then by default eng.traineddata is used.

## Merge unicharsets

all characters are not present in training test. Some rarely occuring characters were to be included. A textfile kha.txt was prepared containing frequent to rarely occuring characters. Then tesstrain.sh comand was used to generate starter traineddata. Only unicharset filewas retained.

## Use combine_lang_model

Replace old starter traineddata generated using tesstrain.sh with new starter traineddata
i. TO make punctuation list

1. cat filename.txt | tr -cd [:punct:] | fold -w 1 | sort | uniq -c | sort -bnr
2. Copy punc.txt of eng and rename it as kha.punc.txt

ii. To make words list
copy & paste the training and eval data in https://www.ltc.lu/enseignants/robert.reyland/wlist/

Result:
char count = 1424716 => 1354036
136807 too short words(s) removed
3133 capital words(s) removed

resulting 125516 words with count were copied to kha.words.txt file
jong (50) – wordcount was removed manually using findall option in sublime editor.

iii. To make numbers list

manually insert the occurences in number.txt file by referencing eng.numbers.txt

Extract base model
extract base model from eng.traineddata usign combine_tessdata and rename it as kha.lstm

## LSTM training

lfx192 spec is used.
max_iterations was set to 300000. although training stops when error rate=0.01. Output info was stored in basetrain.log
LSTM training can be continued from khalayer.checkpoint using –continue-from option

## lstmeval

eval text fiel used here has the same sourceof text used in training textfile.Hence CER=0.08 and word error rate=.19

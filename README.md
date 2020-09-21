# openvoc-keyword-spotting-research-datasets

## Overview

### Reference

This repository contains the license and instructions relative to the open
Datasets mentioned in [this publication](https://arxiv.org/abs/1912.07575):

```
Bluche et al. (2020), "Predicting detection filters for small footprint open-vocabulary keyword spotting"
```

Any publication must include a full citation to this paper.


### Datasets

There have been a lot of interest in the past few years in keyword spotting
focussing on isolated keywords such as speech commands or wake-words.
Several datasets, including training data, have been released openly for these
tasks.

There is however an interest in developing methods to detect keywords defined
at inference time, for which no specific training data can be collected in
sufficient amount in advance.
Most of the reported experiments for open-vocabulary keyword spotting are carried
out on private or paid datasets and vary from one paper to the other.
We feel the the field lacks standard open-access evaluation datasets for this task.

Therefore, we propose two evaluation datasets of spoken queries containing keywords,
aiming at promoting transparency and reproducibility, and at establishing
reference datasets for that specific task.

We crowd-sourced queries for two use-cases: a smart light scenario and a washing machine scenario.
Each dataset was re-recorded in clean and noisy, reverberated far-field conditions with a SNR of 5dB.
Each query contains between one and four keywords, and is expressed in natural language
(e.g. "could you `[turn on]` the lights in the `[bedroom]`").

We selected eight keywords for each task:
`turn on, turn off, increase, decrease, brightness, kitchen, living room, bedroom` for smart lights,
`hot water, cold water, high spin, low spin, wash heavy duty, wash normal, wash colors, wash delicate` for washing machine.

|                                  | lights        | washing       |
|----------------------------------|---------------|---------------|
| Samples                          | 564           | 545           |
| Unique keywords                  | 8             | 8             |
| Speakers (M/F)                   | 32 (22/10)    | 33 (22/11)    |
| Samples/speaker -  avg (min/max) | 18 (8/60)     | 17 (5/50)     |
| Duration (s) - avg (min/max)     | 2.6 (1.6/6.1) | 3.4 (1.8/6.7) |


The datasets are available upon requests as described in the Dataset access
section below.

Please note that the statistics displayed below might not
remain consistent with the datasets provided. Indeed, under the
GDPR and since voice recordings constitute personal data, dataset contributors
have the right to opt out, see
[the full License Terms](https://github.com/sonos/openvoc-keyword-spotting-research-datasets/blob/master/LICENSE)
for more details.




## License summary

Use only for academic and/or research purposes. No commercial use.
Publication permitted only if the Datasets are unmodified and subject to the same license terms.
Any publication must include a full citation to the [paper](https://arxiv.org/abs/1912.07575) in which the
datasets were initially published by Sonos:

```
Bluche et al. (2020), "Predicting detection filters for small footprint open-vocabulary keyword spotting"
```

Please read [the full License Terms](https://github.com/sonos/openvoc-keyword-spotting-research-datasets/blob/master/LICENSE) before accessing the Data Sets.

## Dataset access

To access the data, please fill the following form: 
[https://forms.gle/JtmFYM7xK1SaMfZYA](https://forms.gle/JtmFYM7xK1SaMfZYA)


You will be granted access shortly and will be provided with a temporary url to download it.
The dataset archive contains the following files:
```
smart-lights/
 |-- metadata.json
 |-- clean/
   |-- uuid-id-1.wav
   |-- uuid-id-2.wav
   | ...
 |-- noisy/
   |-- uuid-id-1.wav
   |-- uuid-id-2.wav
   | ...
washing-machine/
 |-- metadata.json
 |-- clean/
   |-- uuid-id-1.wav
   |-- uuid-id-2.wav
   | ...
 |-- noisy/
   |-- uuid-id-1.wav
   |-- uuid-id-2.wav
   | ...
```

The `metadata.json` files contain the list of audios  along with metadata. Each
entry in those lists has the following attributes:

* `keywords`: sequence of keywords to detect in the audio query.
* `transcript`: full transcript of the audio query.
* `filename`: name of the corresponding audio file, in the `clean` and `noisy` subfolders.
* `language`: language of the audio sample (the is only `"en"`, for English, in this version)
* `gender` and `age`: metadata related to the speaker.

An example of such an entry is provided below:

```javascript
"record_b527de37-35e3-48d9-8c8e-3f9672ccdd79_16k_c1": {
    "keywords": [
        "turn off",
        "living room"
    ],
    "language": "en",
    "filename": "record_b527de37-35e3-48d9-8c8e-3f9672ccdd79_16k_c1.wav",
    "transcript": "i want to turn off the lights for the living room",
    "gender": "M",
    "age": 46
}
```

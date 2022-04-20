---
layout: page
title: Competition
permalink: /Competition/
nav_order: 3
---

**[Click here for the Massively Multilingual 2022 Competition on eval.ai](https://eval.ai/web/challenges/challenge-page/1697/overview)**

The Massively Multilingual NLU 2022 Competition is designed to advance the state of the art of massively multilingual natural language understanding, in which a single model can understand and parse text inputs from many different languages.

There are two tasks:

* Full Dataset MMNLU, in which as single model is trained on all languages to perform massively multilingual NLU and is evaluated on all languages, and
* Zero Shot MMNLU, in which a single model is trained only with English data and then is tested on all non-English languages.

Participants are not required to participate in both tasks, and a given participant can make submissions to the two tasks indepedently.

The competition uses the MASSIVE dataset. MASSIVE—Multilingual Amazon Slu resource package (SLURP) for Slot-filling, Intent classification, and Virtual assistant Evaluation—contains 1 million realistic, parallel, labeled virtual assistant text utterances spanning 51 languages, 18 domains, 60 intents, and 55 slots. MASSIVE was created by tasking professional translators to localize or translate the English-only (SLURP dataset) into 50 typologically diverse languages from 29 genera. We have released a paper describing the dataset and presenting initial modeling results on XLM-R and mT5. Tools for the dataset, as well as the modeling code used for our baseline results given in the paper, are available in our Github repository, linked below:

[Download the dataset and see example code here](https://github.com/alexa/massive). The evaluation split will be made available from July 25th through Aug 8th, after which the winner will be chosen. Until then modeling may be performed using the MASSIVE training, validation, and test splits, and submissions may be made to the permanent MASSIVE leaderboard using the test split.

[Read the MASSIVE paper here](https://arxiv.org/abs/2204.08582)

Here is an abbreviated example input to an MMNLU model:

```
{
    "utt": "despiértame a las nueve de la mañana el viernes"
}
```

And here is an abbreviated example output from an MMNLU model:

```
{
    "scenario": "alarm",
    "intent": "alarm_set",
    "annot_utt": "despiértame a las [time : nueve de la mañana] el [date : viernes]"
}
```

Rules:

* All encoder-only models (EX: mBERT and XLM-R) must have fewer than 350M parameters and all sequence-to-sequence models (EX: mT5 and mBART) must have fewer than 700M parameters, including word embeddings. For context, XLM-R Base has 270M parameters, mT5 Base has 580M parameters, and mBART has 680M parameters.
* Any data may be used for training so long as it is publicly available. For example, participants may perform pre-fine-tuning using the open OPUS corpus. As another example, participants may create new training data using a commerical machine translation service, but they must make the resulting dataset available to the community, including for commercial use.
* Dev, test, and eval splits of the MASSIVE dataset may not be used for model training.
* For zero-shot training, only English data from the MASSIVE training split may be used.

Requests:

* Although not required for participation, we encourage all participants to publicly release their code and models under an open source license like MIT or Apache 2.0, and any modifications or additions to the MASSIVE dataset under an open data license like CC BY 4.0.
* We encourage all participants to describe their methods publicly in detail and to submit papers to MMNLU-22.

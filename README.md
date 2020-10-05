# Molweni: A Challenge Multiparty Dialogues-based Machine Reading Comprehension Dataset with Discourse Structure 

We present the Molweni dataset, a machine reading comprehension (MRC) dataset built over multiparty dialogues.
Molweni also uniquely contributes discourse dependency annotations for its multiparty dialogues.
The following shows a multiparty dialogue with four speakers and seven utterances. Due to the property of dialogues, the instances in our corpus could have grammar mistakes. 

| Speaker | Utterance |
|:-------:|-----------|
| `nbx909` |  how do i ﬁnd the address of a usb device ? |
| `Likwidoxigen` | try taking it out to dinner and do a little wine and dine and it shoudl tell ya |
| ` Likwidoxigen` | what sort of device ? |
| `babo` | ca n’t i just copy over the os and leave the data ﬁles untouched ? |
| ` nbx909` | only if you do an upgrade |
| `Nuked` | should i just restart x after installing |
| `Likwidoxigen` | i ’d do a full restart so that it re-loads the modules |

For machine reading comprehension (MRC) , there are two types of questions in our corpus, namely, *answerable questions* and *unanswerable questions*. 
In particular, most of the questions in our dataset are questions leading by Why, What, Who, Where, When and How. Only a small part of the questions are other questions in our dataset, such as questions leading by Do, Which, and Whose. 


* Q1: Why doesLikwidoxigena full restart? 
* A1: it re-loads the modules
* Q2: What doesnbx909want to do?
* A2: ﬁnd the address of a usb device 
* Q3: How to restart network?
* A3: NA.



## Dataset

Our dataset derives from the large scale multiparty dialogues dataset the Ubuntu Chat Corpus (Lowe et al., 2015). The Ubuntu dataset is a large scale multiparty dialogues corpus. We adopt the dialogues with 8-15 utterances and 2-9 speakers. To simplify the task, we ﬁlter the dialogues with long sentences (more than 20 words).
We choose 10,000 dialogues with 88,303 utterances from the Ubuntu dataset , including 78,246 discourse relations and 32,700 questions for machine reading comprehension. 
The average speakers per dialogue in our dataset is 3.52 , the average and max length of dialogues are respectively 8.83 and 14 utterances. The number of answerable questions and unanswerable questions are 27,269 and 5,115. 

| Metric | Number |
|:-------:|-----------|
| Avg./Max. of speakers per dialogue | 3.52 / 9 |
| Avg./Max. question length (in tokens) | 5.86 / 18 |
| Avg./Max. answer length (in tokens) | 3.82 / 19 |
| Avg./Max. dialogue length (in tokens)  | 85 / 169 |
| Avg./Max. dialogue length (in utterances) | 8.83 / 14 |
| Questions per dialogue in Train/Dev | 3 |
| Questions per dialogue in Test | 30 |
| Vocabulary size | 17,924 |
| Answerable questions | 26,376 |
| Unanswerable questions | 4,386 |
* Latest release: [v1.0](https://github.com/HIT-SCIR/Molweni)

## Statistics

The overview of Molweni for MRC:

| Dataset | Dialogues | Questions |Utterances|
| :-----: | --------: | --------: | ------: |
|   TRAIN   |     9,000 |    27,000 |  79,487 |
|   DEV   |       900 |     2,700 |   7,971 |
|   TEST   |       100 |     3,000 |     845 |


## Citation
* [Molweni: A Challenge Multiparty Dialogues-based Machine Reading Comprehension Dataset with Discourse Structure](https://arxiv.org/abs/2004.05080).Jiaqi Li, Ming Liu, Min-Yen Kan, Zihao Zheng, Zekun Wang, Wenqiang Lei, Ting Liu, Bing Qin. Proceedings of the 28th International Conference on Computational Linguistics (COLING  2020).


## Annotation
ALL the datas are in the "data" field. And the "data" field has two keys . The first is "title" which shows the kind of data , including test,train and dev.
The scond is "dialogues" which is a list of every dialogue's information .

```json
{
	"data": 
		{"title": "test",
		"dialogues": [
			{
                "edus": [
					{
                        "text": "that i use between linux and windows",
                        "speaker": "JuJuBee_"
                    },
                    {
                        "text": "did you mount it with fstab ? give us a pastebin of the fstab that is probably it eh.EMOJI",
                        "speaker": "nit-wit"
                    },
                    {
                        "text": "it 's treated as a mount mask",
                        "speaker": "ikonia"
                    }
				],
				"context": "jujubee_: that i use between linux and windows nit-wit: did you mount it with fstab ? give us a pastebin of the fstab that is probably it eh.emoji ikonia: it 's treated as a mount mask",
				"qas": [
					{
                        "question": "Where does JuJuBee_ use ?",
                        "id": "3f45971d1b432a674e1098bb80ebe70c",
                        "answers": [
                            {
                                "text": "between linux and windows",
                                "answer_start": 21
                            }
                        ],
                        "is_impossible": false
                    }
				],
				"relations": [
					{
                        "y": 1,
                        "x": 0,
                        "type": "Clarification_question"
                    },
                    {
                        "y": 2,
                        "x": 0,
                        "type": "Comment"
                    }
				]
			}
		]
	}
}
```
The information of the keys in the "dialogues" field are as follows.
The "edus" field is a list of utterances which contains the speaker and the text.
The "context" field is a string of the dialogue.
The "qas" field includes questions and the answers.
The "relations" field is a list of relations between two utterances,and classify the sense of relations.

## Contact

* [Ming Liu](http://homepage.hit.edu.cn/liuming1981).

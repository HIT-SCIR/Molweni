# Molweni: A Challenge Multiparty Dialogues-based Machine Reading Comprehension Dataset with Discourse Structure 

We present the Molweni dataset, a machine reading comprehension (MRC) dataset built over multiparty dialogues.
Molweni also uniquely contributes discourse dependency annotations for its multiparty dialogues.
The following shows a multiparty dialogue with four speakers and seven utterances. Due to the property of dialogues, the dialogue instances in our corpus could have grammar mistakes. There are two versions of the Molweni dataset that can be respectively used for machine reading comprehension (MRC) and discourse parsing (DP). Both two versions of Molweni come from the same 10K dialogue, but the data partition is different.

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


* Q1: Why does Likwidoxigena full restart? 
* A1: it re-loads the modules
* Q2: What does nbx909 want to do?
* A2: ﬁnd the address of a usb device 
* Q3: How to restart network?
* A3: NA.



## Dataset

Our dataset derives from the large scale multiparty dialogues dataset the Ubuntu Chat Corpus (Lowe et al., 2015). The Ubuntu dataset is a large scale multiparty dialogues corpus. We adopt the dialogues with 8-15 utterances and 2-9 speakers. To simplify the task, we ﬁlter the dialogues with long sentences (more than 20 words).
We choose 10,000 dialogues with 88,303 utterances from the Ubuntu dataset , including 78,245 discourse relations and 30,046 questions for machine reading comprehension. 
The average speakers per dialogue in our dataset is 3.52 , the average and max length of dialogues are respectively 8.83 and 14 utterances. The number of answerable questions and unanswerable questions are 25,759 and 4,287. 

| Metric | Number |
|:-------:|-----------|
| Avg./Max. of speakers per dialogue | 3.51 / 9 |
| Avg./Max. question length (in tokens) | 5.91 / 19 |
| Avg./Max. answer length (in tokens) | 4.08 / 19 |
| Avg./Max. dialogue length (in tokens)  | 104.4 / 208 |
| Avg./Max. dialogue length (in utterances) | 8.82 / 14 |
| Avg./Max. utterance length (in tokens) | 10.8 / 19 |
| Vocabulary size | 24,615 |
| Answerable questions | 25,779 |
| Unanswerable questions | 4,287 |
* Latest release: [v1.0](https://github.com/HIT-SCIR/Molweni)

## Statistics

The overview of Molweni for MRC(withDiscourse):

| Dataset | Dialogues | Utterances | Questions |
| :-----: | --------: | --------: | ------: |
|   TRAIN   |     8,771 | 77,374 |  24,682 |
|   DEV   |       883 |     7,823 |   2,513 |
|   TEST   |       100 |     845 |     2,871 |


The overview of Molweni for Discourse parsing:

| Dataset | Dialogues | Utterances | Relations |
| :-----: | --------: | --------: | ------: |
|   TRAIN   |   9,000 | 79,487 |  70,454 |
|   DEV   |     500 |     4,386 |  3,880 |
|   TEST   |    500 |     4,430 |  3,911 |


## Citation
* [Molweni: A Challenge Multiparty Dialogues-based Machine Reading Comprehension Dataset with Discourse Structure](https://www.aclweb.org/anthology/2020.coling-main.238/).Jiaqi Li, Ming Liu, Min-Yen Kan, Zihao Zheng, Zekun Wang, Wenqiang Lei, Ting Liu, Bing Qin. Proceedings of the 28th International Conference on Computational Linguistics (COLING  2020).

* @inproceedings{li-etal-2020-molweni,  <br>
    title = "Molweni: A Challenge Multiparty Dialogues-based Machine Reading Comprehension Dataset with Discourse Structure",  <br>
    author = "Li, Jiaqi  and  <br>
      Liu, Ming  and  <br>
      Kan, Min-Yen  and <br>
      Zheng, Zihao  and <br>
      Wang, Zekun  and <br>
      Lei, Wenqiang  and <br>
      Liu, Ting  and <br>
      Qin, Bing", <br>
    booktitle = "Proceedings of the 28th International Conference on Computational Linguistics", <br>
    month = dec, <br>
    year = "2020", <br>
    address = "Barcelona, Spain (Online)", <br>
    publisher = "International Committee on Computational Linguistics", <br>
    url = "https://www.aclweb.org/anthology/2020.coling-main.238", <br>
    pages = "2642--2652", <br>
    abstract = "Research into the area of multiparty dialog has grown considerably over recent years. We present the Molweni dataset, a machine reading comprehension (MRC) dataset with discourse structure built over multiparty dialog. Molweni{'}s source samples from the Ubuntu Chat Corpus, including 10,000 dialogs comprising 88,303 utterances. We annotate 30,066 questions on this corpus, including both answerable and unanswerable questions. Molweni also uniquely contributes discourse dependency annotations in a modified Segmented Discourse Representation Theory (SDRT; Asher et al., 2016) style for all of its multiparty dialogs, contributing large-scale (78,245 annotated discourse relations) data to bear on the task of multiparty dialog discourse parsing. Our experiments show that Molweni is a challenging dataset for current MRC models: BERT-wwm, a current, strong SQuAD 2.0 performer, achieves only 67.7{\%} F1 on Molweni{'}s questions, a 20+{\%} significant drop as compared against its SQuAD 2.0 performance.", <br>
} <br>

## Annotation
ALL the datas are in the "data" field. And the "data" field has two keys . The first is "title" which shows the kind of data , including test,train and dev.
The scond is "dialogues" which is a list of every dialogue's information .

```json
{
    "data": {
        "title": "test", 
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

## Acknowledgments

Thanks to Prof. [Min-Yen Kan](https://www.comp.nus.edu.sg/~kanmy/index.html) and Dr. Wenqiang Lei of National University of Singapore. Thanks to Zihao Zheng, Zekun Wang, Yibo Sun, Tianwen Jiang, Daxing Zhang, Rongtian Bian, Heng Zhang, Zhenyu Hu and other students of Harbin Institute of Technology for their support in the process of data set annotation. Thanks to Wenpeng Hu, a Ph.D. student of Peking University, for providing preprocessed Ubuntu data.

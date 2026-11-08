# Emotion Detector — Submission answers

Repo: https://github.com/Ishan-014/oaqjp-final-project-emb-ai

> The Watson NLP endpoint (`sn-watson-emotion.labs.skills.network`) only answers from inside the
> IBM Skills Network lab. Every terminal output and screenshot marked **LAB** below has to be
> captured there. Open the lab terminal, then run:
>
> ```
> cd /home/project
> git clone https://github.com/Ishan-014/oaqjp-final-project-emb-ai.git
> cd oaqjp-final-project-emb-ai
> python3.11 -m pip install flask requests pylint
> ```

## Task 1 — GitHub repository URL

https://github.com/Ishan-014/oaqjp-final-project-emb-ai/blob/main/README.md

## Task 2 — Emotion detection application

**2a code:** paste [2a_emotion_detection.py](2a_emotion_detection.py).

**2b terminal output (LAB):**

```
python3.11
>>> from emotion_detection import emotion_detector
```

That import needs a top-level `emotion_detection.py`, so before Task 4 copy it:
`cp 2a_emotion_detection.py emotion_detection.py`, then in the Python shell:

```
>>> from emotion_detection import emotion_detector
>>> emotion_detector("I love this new technology.")
```

Screenshot or copy the JSON text it prints.

## Task 3 — Output formatting

**3a code:** paste [3a_output_formatting.py](3a_output_formatting.py).

**3b terminal output (LAB):** `cp 3a_output_formatting.py emotion_detection.py`, then:

```
python3.11
>>> from emotion_detection import emotion_detector
>>> emotion_detector("I am so happy I am doing this.")
```

Expected shape: `{'anger': ..., 'disgust': ..., 'fear': ..., 'joy': ..., 'sadness': ..., 'dominant_emotion': 'joy'}`.
Afterwards `rm emotion_detection.py` so it doesn't shadow the package.

## Task 4 — EmotionDetection package

**4a URL:** https://github.com/Ishan-014/oaqjp-final-project-emb-ai/blob/main/EmotionDetection/__init__.py

**4b terminal output (LAB, also works offline):**

```
python3.11
>>> import EmotionDetection
>>> from EmotionDetection.emotion_detection import emotion_detector
>>> emotion_detector("I hate working long hours.")
```

Expected `dominant_emotion`: `'anger'`.

## Task 5 — Unit tests

**5a code:** paste [5a_unit_testing.py](5a_unit_testing.py) (same as `test_emotion_detection.py`).

**5b terminal output (LAB):** `python3.11 test_emotion_detection.py` — expected:

```
.
----------------------------------------------------------------------
Ran 1 test in ...s

OK
```

## Task 6 — Flask deployment

**6a code:** paste [6a_server.py](6a_server.py).

**6b screenshot (LAB):** `python3.11 server.py`, open port 5000 via *Skills Network Toolbox → Launch
Application*, type `I think I am having fun`, click **Run Sentiment Analysis**, screenshot the
page with the result → save as `6b_deployment_test.png`.

## Task 7 — Error handling

**7a code:** paste [7a_error_handling_function.py](7a_error_handling_function.py) (the
`status_code == 400` branch returning all `None`).

**7b code:** paste [7b_error_handling_server.py](7b_error_handling_server.py) (the
`if response['dominant_emotion'] is None` → `"Invalid text! Please try again!"` branch).

**7c screenshot (LAB):** with the server running, leave the text box empty and click
**Run Sentiment Analysis**; the page shows `Invalid text! Please try again!` → save as
`7c_error_handling_interface.png`.

## Task 8 — Static code analysis

**8a code:** paste [8a_server_modified.py](8a_server_modified.py).

**8b terminal output:** `pylint server.py`

```
--------------------------------------------------------------------
Your code has been rated at 10.00/10
```

(Verified locally with pylint 4.1.3 on 2026-11-08.)

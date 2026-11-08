# Emotion Detector — Submission answers

Repo: https://github.com/Ishan-014/oaqjp-final-project-emb-ai

> The Watson NLP endpoint only answers from inside the IBM Skills Network lab, so every
> terminal output and screenshot (Q3, Q5, Q7, Q9, Q11, Q14, Q16) must be captured there.
> The graders want the path `/home/project/final_project` in the outputs, so clone into
> that folder name. In a lab terminal:
>
> ```
> cd /home/project
> git clone https://github.com/Ishan-014/oaqjp-final-project-emb-ai.git final_project
> cd final_project
> python3 -m pip install flask requests pylint
> ```

| Q | Task | What to submit |
|---|------|----------------|
| 1 | 1 | https://github.com/Ishan-014/oaqjp-final-project-emb-ai/blob/main/README.md |
| 2 | 2a | Contents of `2a_emotion_detection.py` |
| 3 | 2b | Lab terminal output, steps below |
| 4 | 3a | Contents of `3a_output_formatting.py` |
| 5 | 3b | Lab terminal output, steps below |
| 6 | 4a | https://github.com/Ishan-014/oaqjp-final-project-emb-ai/blob/main/EmotionDetection/__init__.py |
| 7 | 4b | Lab terminal output, steps below |
| 8 | 5a | Contents of `5a_unit_testing.py` |
| 9 | 5b | Lab terminal output, steps below |
| 10 | 6a | Contents of `6a_server.py` |
| 11 | 6b | Upload `6b_deployment_test.png`, steps below |
| 12 | 7a | Contents of `7a_error_handling_function.py` |
| 13 | 7b | Contents of `7b_error_handling_server.py` |
| 14 | 7c | Upload `7c_error_handling_interface.png`, steps below |
| 15 | 8a | Contents of `8a_server_modified.py` |
| 16 | 8b | Lab terminal output, steps below |

## Q3 — 2b application creation

```
cp 2a_emotion_detection.py emotion_detection.py
python3
>>> from emotion_detection import emotion_detector
>>> print(emotion_detector('I am really mad about this'))
>>> exit()
python3 test_emotion_detection.py
```

Copy everything from the `python3` prompt line down to the `OK` line.

## Q5 — 3b formatted output

```
cp 3a_output_formatting.py emotion_detection.py
python3
>>> from emotion_detection import emotion_detector
>>> print(emotion_detector('I am so happy I am doing this'))
>>> exit()
rm emotion_detection.py
```

Output is a dict with anger, disgust, fear, joy, sadness and `'dominant_emotion': 'joy'`.

## Q7 — 4b packaging test

```
python3 -c "from EmotionDetection.emotion_detection import emotion_detector; print(emotion_detector('I am very angry'))"
```

Paste the command line and the dict (`'dominant_emotion': 'anger'`).

## Q9 — 5b unit tests

```
python3 test_emotion_detection.py
```

Expected: `Ran 1 test in ...s` then `OK`.

## Q11 — 6b deployment screenshot

1. `python3 server.py` (leave it running).
2. Skills Network Toolbox → Other → Launch Application → port `5000`.
3. Type `I think I am having fun`, click **Run Sentiment Analysis**.
4. Screenshot showing the typed text and the result line → `6b_deployment_test.png`.

## Q14 — 7c error handling screenshot

Same page, clear the text box, click **Run Sentiment Analysis**. Screenshot showing
`Invalid text! Please try again!` → `7c_error_handling_interface.png`.

## Q16 — 8b static code analysis

Stop the server (Ctrl+C), then:

```
pylint server.py
```

Expected: `Your code has been rated at 10.00/10` (verified locally with pylint 4.1.3).

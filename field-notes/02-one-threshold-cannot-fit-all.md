# A 21.5% precision complaint, solved by thresholds

**Customer:** a global entertainment company. **My role:** founding sales engineer at Coactive AI.

## Situation

Our platform tags video frames: objects, emotions, gestures and more. Each tag has a confidence score, and a threshold decides which tags to keep. Precision is the share of kept tags that are correct. The customer measured our tags at 21.5% precision and asked why.

## What I measured

- I split the result by tag category. The single number hid a wide range:

  | Category | Precision |
  |---|---|
  | Objects | 75–100% |
  | Emotions | 5–14% |
  | Gestures | 0–8% |

- The confidence scores sat in a narrow band, from 0.98 to 0.9999. In a band that narrow, one shared threshold cannot separate correct tags from wrong ones across categories.

## What I decided

- I set a threshold for each tag, not one for all tags. Tags per frame fell from 10 to 1.9.
- Recall is the share of true matches that the system finds. Later, a face-recognition model upgrade appeared to halve recall. I traced the drop to thresholds that were tuned to the old model, not to the new model itself.

## Result

- F1 is one score that combines precision and recall. With thresholds tuned to the new model, F1 came back to 0.93–0.99 across 199 videos.
- I wrote both cases up as a per-category root-cause guide.

## What I tell the next customer

- Split a precision number by category before you judge the model. An average can hide a category that works well and one that does not work at all.
- Look at the score distribution. When scores bunch in a narrow band, set thresholds per tag.
- Tune thresholds again after every model change, before you compare results. A new model moves the scores, so old thresholds give misleading numbers.
